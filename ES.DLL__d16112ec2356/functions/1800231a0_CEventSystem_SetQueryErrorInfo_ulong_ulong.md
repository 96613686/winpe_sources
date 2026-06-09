# CEventSystem::SetQueryErrorInfo(ulong,ulong,...)

- ea: `0x1800231a0`
- end: `0x180023355`
- name: `?SetQueryErrorInfo@CEventSystem@@AEAAXKKZZ`
- size: `437`
- prototype: `void(CEventSystem *__hidden this, unsigned int, unsigned int, ...)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021e40`
- `0x180022e50`

## callees

- `0x18000c910`
- `0x1800231a0`
- `0x1800434c6`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002323e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002323e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800231f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800231f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023252`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180023252`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180023308`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180023308`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180023281`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180023281`

## string_xrefs

- `0x1800231ee`: `comres.dll`

## pseudocode

```c
void CEventSystem::SetQueryErrorInfo(CEventSystem *this, DWORD a2, unsigned int a3, ...)
{
  HMODULE Library; // rdi
  DWORD v5; // ebx
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp-1048h] BYREF
  IErrorInfo *perrinfo; // [rsp+48h] [rbp-1040h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-1038h] BYREF
  WCHAR Buffer[2048]; // [rsp+60h] [rbp-1028h] BYREF
  va_list va; // [rsp+10A8h] [rbp+20h] BYREF

  va_start(va, a3);
  Arguments = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  if ( Library )
  {
    va_copy(Arguments, va);
    v5 = FormatMessageW(0x8FFu, Library, a2, 0, Buffer, 0x800u, &Arguments);
    Arguments = 0;
    FreeLibrary(Library);
    if ( v5 == (unsigned int)safe_lstrlenW(Buffer) )
    {
      pperrinfo = 0;
      perrinfo = 0;
      if ( CreateErrorInfo(&pperrinfo) >= 0
        && ((int (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &IID_IEventSystem) >= 0
        && ((int (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
             pperrinfo,
             L"EventSystem.EventSystem") >= 0
        && ((int (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, Buffer) >= 0
        && ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &IID_IErrorInfo,
             &perrinfo) >= 0 )
      {
        SetErrorInfo(0, perrinfo);
      }
      if ( perrinfo )
        ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
      if ( pperrinfo )
        ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    }
  }
}

```

## disassembly

```asm
0x1800231a0  mov     [rsp+arg_10], r8d
0x1800231a5  mov     [rsp+arg_18], r9
0x1800231aa  push    rbx
0x1800231ab  push    rdi
0x1800231ac  mov     eax, 1078h
0x1800231b1  call    _alloca_probe
0x1800231b6  sub     rsp, rax
0x1800231b9  mov     rax, cs:__security_cookie
0x1800231c0  xor     rax, rsp
0x1800231c3  mov     [rsp+1088h+var_28], rax
0x1800231cb  mov     ebx, edx
0x1800231cd  mov     [rsp+1088h+var_1038], 0
0x1800231d6  xor     edx, edx; Val
0x1800231d8  mov     r8d, 1000h; Size
0x1800231de  lea     rcx, [rsp+1088h+Buffer]; void *
0x1800231e3  call    memset_0
0x1800231e8  xor     edx, edx; hFile
0x1800231ea  lea     r8d, [rdx+2]; dwFlags
0x1800231ee  lea     rcx, LibFileName; "comres.dll"
0x1800231f5  call    cs:__imp_LoadLibraryExW
0x1800231fb  mov     rdi, rax
0x1800231fe  test    rax, rax
0x180023201  jz      loc_18002333B
0x180023207  lea     rax, [rsp+1088h+arg_18]
0x18002320f  mov     [rsp+1088h+var_1038], rax
0x180023214  lea     rax, [rsp+1088h+var_1038]
0x180023219  mov     [rsp+1088h+Arguments], rax; Arguments
0x18002321e  mov     [rsp+1088h+nSize], 800h; nSize
0x180023226  lea     rax, [rsp+1088h+Buffer]
0x18002322b  mov     [rsp+1088h+lpBuffer], rax; lpBuffer
0x180023230  xor     r9d, r9d; dwLanguageId
0x180023233  mov     r8d, ebx; dwMessageId
0x180023236  mov     rdx, rdi; lpSource
0x180023239  mov     ecx, 8FFh; dwFlags
0x18002323e  call    cs:__imp_FormatMessageW
0x180023244  mov     ebx, eax
0x180023246  mov     [rsp+1088h+var_1038], 0
0x18002324f  mov     rcx, rdi; hLibModule
0x180023252  call    cs:__imp_FreeLibrary
0x180023258  lea     rcx, [rsp+1088h+Buffer]; unsigned __int16 *
0x18002325d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180023262  cmp     ebx, eax
0x180023264  jnz     loc_18002333B
0x18002326a  mov     [rsp+1088h+pperrinfo], 0
0x180023273  mov     [rsp+1088h+perrinfo], 0
0x18002327c  lea     rcx, [rsp+1088h+pperrinfo]; pperrinfo
0x180023281  call    cs:__imp_CreateErrorInfo
0x180023287  test    eax, eax
0x180023289  js      loc_18002330F
0x18002328f  mov     rcx, [rsp+1088h+pperrinfo]
0x180023294  mov     rax, [rcx]
0x180023297  lea     rdx, IID_IEventSystem
0x18002329e  mov     rax, [rax+18h]
0x1800232a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232a7  test    eax, eax
0x1800232a9  js      short loc_18002330F
0x1800232ab  mov     rcx, [rsp+1088h+pperrinfo]
0x1800232b0  mov     rax, [rcx]
0x1800232b3  lea     rdx, aEventsystemEve; "EventSystem.EventSystem"
0x1800232ba  mov     rax, [rax+20h]
0x1800232be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232c3  test    eax, eax
0x1800232c5  js      short loc_18002330F
0x1800232c7  mov     rcx, [rsp+1088h+pperrinfo]
0x1800232cc  mov     rax, [rcx]
0x1800232cf  lea     rdx, [rsp+1088h+Buffer]
0x1800232d4  mov     rax, [rax+28h]
0x1800232d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232dd  test    eax, eax
0x1800232df  js      short loc_18002330F
0x1800232e1  mov     rcx, [rsp+1088h+pperrinfo]
0x1800232e6  mov     rax, [rcx]
0x1800232e9  lea     r8, [rsp+1088h+perrinfo]
0x1800232ee  lea     rdx, IID_IErrorInfo
0x1800232f5  mov     rax, [rax]
0x1800232f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232fd  test    eax, eax
0x1800232ff  js      short loc_18002330F
0x180023301  mov     rdx, [rsp+1088h+perrinfo]; perrinfo
0x180023306  xor     ecx, ecx; dwReserved
0x180023308  call    cs:__imp_SetErrorInfo
0x18002330e  nop
0x18002330f  mov     rcx, [rsp+1088h+perrinfo]
0x180023314  test    rcx, rcx
0x180023317  jz      short loc_180023325
0x180023319  mov     rax, [rcx]
0x18002331c  mov     rax, [rax+10h]
0x180023320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023325  mov     rcx, [rsp+1088h+pperrinfo]
0x18002332a  test    rcx, rcx
0x18002332d  jz      short loc_18002333B
0x18002332f  mov     rax, [rcx]
0x180023332  mov     rax, [rax+10h]
0x180023336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002333b  mov     rcx, [rsp+1088h+var_28]
0x180023343  xor     rcx, rsp; StackCookie
0x180023346  call    __security_check_cookie
0x18002334b  add     rsp, 1078h
0x180023352  pop     rdi
0x180023353  pop     rbx
0x180023354  retn
0x180044e1e  push    rbp
0x180044e20  sub     rsp, 40h
0x180044e24  mov     rbp, rdx
0x180044e27  mov     rcx, [rbp+48h]
0x180044e2b  test    rcx, rcx
0x180044e2e  jz      short loc_180044E3D
0x180044e30  mov     rax, [rcx]
0x180044e33  mov     rax, [rax+10h]
0x180044e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e3c  nop
0x180044e3d  mov     rcx, [rbp+40h]
0x180044e41  test    rcx, rcx
0x180044e44  jz      short loc_180044E53
0x180044e46  mov     rax, [rcx]
0x180044e49  mov     rax, [rax+10h]
0x180044e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e52  nop
0x180044e53  add     rsp, 40h
0x180044e57  pop     rbp
0x180044e58  retn
```
