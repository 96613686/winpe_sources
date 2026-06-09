# LoadPersistR(void)

- ea: `0x18001687c`
- end: `0x180016a4a`
- name: `?LoadPersistR@@YAXXZ`
- size: `462`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800167e4`

## callees

- `0x180001838`
- `0x180009e0c`
- `0x18001687c`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e060`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800168be`
- `KERNEL32!GetModuleFileNameW` at `0x1800168be`
- `KERNEL32!LoadLibraryExW` at `0x1800169cb`
- `KERNEL32!LoadLibraryExW` at `0x1800169cb`

## string_xrefs

- `0x180016964`: `msdaprsr.dll`

## pseudocode

```c
void LoadPersistR(void)
{
  int v0; // eax
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // rdx
  int v3; // eax
  int v4; // ebx
  WCHAR Filename[256]; // [rsp+30h] [rbp-218h] BYREF

  if ( !g_hinstance_PersistR )
  {
    LOWORD(v0) = GetModuleFileNameW(g_hInstancePersistMain, Filename, 0xFFu);
    if ( (__int16)v0 <= 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048AD0[0] )
          bidTraceW(off_1800481E8[0], 71680, off_180048AD0[0], 2147500037LL, 70);
      }
      goto LABEL_22;
    }
    v0 = (__int16)v0;
    do
      v1 = v0--;
    while ( Filename[v0] != 92 );
    v2 = v1;
    if ( v2 >= 256 )
      _report_rangecheckfailure();
    Filename[v2] = 0;
    if ( (unsigned __int64)(v0 + 12LL) >= 0xFF )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048AC8[0] )
        bidTraceW(off_1800481E8[0], 82944, off_180048AC8[0], 2147500037LL, 81);
      goto LABEL_22;
    }
    v3 = StringCchCatW(Filename, 0x100u, L"msdaprsr.dll");
    v4 = v3;
    if ( v3 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048AC0[0] )
        bidTraceW(off_1800481E8[0], 86016, off_180048AC0[0], (unsigned int)v3, 84);
      ThrowHR(v4);
    }
    g_hinstance_PersistR = LoadLibraryExW(Filename, 0, 8u);
    if ( !g_hinstance_PersistR )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048AB8[0] )
        bidTraceW(off_1800481E8[0], 92160, off_180048AB8[0], 2147500037LL, 90);
LABEL_22:
      ThrowHR(-2147467259);
    }
  }
}

```

## disassembly

```asm
0x18001687c  mov     [rsp+arg_0], rbx
0x180016881  push    rdi
0x180016882  sub     rsp, 240h
0x180016889  mov     rax, cs:__security_cookie
0x180016890  xor     rax, rsp
0x180016893  mov     [rsp+248h+var_18], rax
0x18001689b  xor     edi, edi
0x18001689d  cmp     cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hinstance_PersistR
0x1800168a4  jnz     loc_180016A29
0x1800168aa  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; hModule
0x1800168b1  lea     rdx, [rsp+248h+Filename]; lpFilename
0x1800168b6  mov     ebx, 0FFh
0x1800168bb  mov     r8d, ebx; nSize
0x1800168be  call    cs:__imp_GetModuleFileNameW
0x1800168c4  test    ax, ax
0x1800168c7  jg      short loc_1800168FF
0x1800168c9  test    byte ptr cs:_bidGblFlags, 2
0x1800168d0  jz      loc_180016A18
0x1800168d6  mov     rax, cs:off_180048AD0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x1800168dd  test    rax, rax
0x1800168e0  jz      loc_180016A18
0x1800168e6  mov     r8, cs:off_180048AD0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x1800168ed  mov     edx, 11800h
0x1800168f2  mov     [rsp+248h+var_228], 46h ; 'F'
0x1800168fa  jmp     loc_180016A06
0x1800168ff  cwde
0x180016900  movsxd  rdx, eax
0x180016903  dec     eax
0x180016905  movsxd  rcx, eax
0x180016908  cmp     [rsp+rcx*2+248h+Filename], 5Ch ; '\'
0x18001690e  jnz     short loc_180016900
0x180016910  add     rdx, rdx
0x180016913  cmp     rdx, 200h
0x18001691a  jnb     loc_180016A23
0x180016920  lea     rax, [rcx+0Ch]
0x180016924  mov     [rsp+rdx+248h+Filename], di
0x180016929  cmp     rax, rbx
0x18001692c  jb      short loc_180016964
0x18001692e  test    byte ptr cs:_bidGblFlags, 2
0x180016935  jz      loc_180016A18
0x18001693b  mov     rax, cs:off_180048AC8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016942  test    rax, rax
0x180016945  jz      loc_180016A18
0x18001694b  mov     r8, cs:off_180048AC8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016952  mov     edx, 14400h
0x180016957  mov     [rsp+248h+var_228], 51h ; 'Q'
0x18001695f  jmp     loc_180016A06
0x180016964  lea     r8, aMsdaprsrDll; "msdaprsr.dll"
0x18001696b  mov     edx, 100h; unsigned __int64
0x180016970  lea     rcx, [rsp+248h+Filename]; unsigned __int16 *
0x180016975  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001697a  mov     ebx, eax
0x18001697c  test    eax, eax
0x18001697e  jns     short loc_1800169C0
0x180016980  test    byte ptr cs:_bidGblFlags, 2
0x180016987  jz      short loc_1800169B8
0x180016989  mov     rcx, cs:off_180048AC0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x180016990  test    rcx, rcx
0x180016993  jz      short loc_1800169B8
0x180016995  mov     r8, cs:off_180048AC0; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x18001699c  mov     r9d, eax
0x18001699f  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800169a6  mov     edx, 15000h
0x1800169ab  mov     [rsp+248h+var_228], 54h ; 'T'
0x1800169b3  call    _bidTraceW
0x1800169b8  mov     ecx, ebx; int
0x1800169ba  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800169c0  xor     edx, edx; hFile
0x1800169c2  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x1800169c7  lea     r8d, [rdx+8]; dwFlags
0x1800169cb  call    cs:__imp_LoadLibraryExW
0x1800169d1  mov     cs:?g_hinstance_PersistR@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinstance_PersistR
0x1800169d8  test    rax, rax
0x1800169db  jnz     short loc_180016A29
0x1800169dd  test    byte ptr cs:_bidGblFlags, 2
0x1800169e4  jz      short loc_180016A18
0x1800169e6  mov     rax, cs:off_180048AB8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x1800169ed  test    rax, rax
0x1800169f0  jz      short loc_180016A18
0x1800169f2  mov     r8, cs:off_180048AB8; "<LoadPersistR|ADO|ERR>  HRESULT: 0x%08x"...
0x1800169f9  mov     edx, 16800h
0x1800169fe  mov     [rsp+248h+var_228], 5Ah ; 'Z'
0x180016a06  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016a0d  mov     r9d, 80004005h
0x180016a13  call    _bidTraceW
0x180016a18  mov     ecx, 80004005h; int
0x180016a1d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016a23  call    __report_rangecheckfailure
0x180016a29  mov     rcx, [rsp+248h+var_18]
0x180016a31  xor     rcx, rsp; StackCookie
0x180016a34  call    __security_check_cookie
0x180016a39  mov     rbx, [rsp+248h+arg_0]
0x180016a41  add     rsp, 240h
0x180016a48  pop     rdi
0x180016a49  retn
```
