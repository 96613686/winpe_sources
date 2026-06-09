# ExceptionId(_GUID const &,uint,uint,long)

- ea: `0x1800406b0`
- end: `0x180040877`
- name: `?ExceptionId@@YAXAEBU_GUID@@IIJ@Z`
- size: `455`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned int, int)`
- caller_count: `103`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a6d0`
- `0x18000ca50`
- `0x1800138d4`
- `0x180017ac0`
- `0x1800183f0`
- `0x180018de0`
- `0x180019090`
- `0x180032154`
- `0x1800323c0`
- `0x180032490`
- `0x1800330c0`
- `0x180033210`
- `0x1800332c0`
- `0x180033430`
- `0x180033600`
- `0x180033750`
- `0x180035c34`
- `0x180036090`
- `0x180036b40`
- `0x1800384cc`
- `0x180039428`
- `0x18003ab50`
- `0x18003af10`
- `0x18003b320`
- `0x18003b410`
- `0x18003b530`
- `0x18003b590`
- `0x18003b8b0`
- `0x180047440`
- `0x18004aa50`
- `0x18004ad4c`
- `0x18004ae38`
- `0x18004b0f4`
- `0x18004b34c`
- `0x18004bce8`
- `0x18004d090`
- `0x18004d740`
- `0x18004d9b0`
- `0x18004dec0`
- `0x18004e430`
- `0x18004e890`
- `0x18004ece0`
- `0x18004f030`
- `0x18004f610`
- `0x18004f950`
- `0x18004fca0`
- `0x180050000`
- `0x180050360`
- `0x180050910`
- `0x180050c80`

## callees

- `0x180023dd0`
- `0x180023e60`
- `0x1800406b0`
- `0x180040b18`
- `0x180040e8c`
- `0x180064010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800407ed`
- `msvcrt!swprintf_s` at `0x1800407ed`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004070f`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18004070f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180040720`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180040832`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180040720`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180040832`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180040730`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180040730`

## pseudocode

```c
void __fastcall ExceptionId(const struct _GUID *a1, UINT a2, UINT a3, int a4)
{
  ICreateErrorInfo *v8; // [rsp+20h] [rbp-E0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Destination[256]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v11[1024]; // [rsp+230h] [rbp+130h] BYREF
  wchar_t Format[1024]; // [rsp+A30h] [rbp+930h] BYREF
  wchar_t Buffer[1024]; // [rsp+1230h] [rbp+1130h] BYREF

  v8 = 0;
  pperrinfo = 0;
  if ( a3 == 100 )
    _InterlockedIncrement(&g_nOOMErrors);
  if ( GetErrorInfo(0, &pperrinfo) )
  {
    if ( CreateErrorInfo(&v8) >= 0 )
    {
      ((void (__fastcall *)(ICreateErrorInfo *, const struct _GUID *))v8->lpVtbl->SetGUID)(v8, a1);
      ((void (__fastcall *)(ICreateErrorInfo *, __int64 *))v8->lpVtbl->SetHelpFile)(v8, &qword_18006C238);
      ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))v8->lpVtbl->SetHelpContext)(v8, 0);
      if ( (unsigned int)CwchLoadStringOfId(a2, v11, 1024) )
        ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))v8->lpVtbl->SetSource)(v8, v11);
      if ( (unsigned int)CwchLoadStringOfId(a3, Format, 1024) )
      {
        HResultToWsz(a4, Destination, 0x100u);
        swprintf_s(Buffer, 0x400u, Format, Destination);
        ((void (__fastcall *)(ICreateErrorInfo *, wchar_t *))v8->lpVtbl->SetDescription)(v8, Buffer);
      }
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v8->lpVtbl->QueryInterface)(
             v8,
             &IID_IErrorInfo,
             &pperrinfo) >= 0 )
      {
        SetErrorInfo(0, pperrinfo);
        ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      }
      ((void (__fastcall *)(ICreateErrorInfo *))v8->lpVtbl->Release)(v8);
    }
  }
  else
  {
    SetErrorInfo(0, pperrinfo);
  }
}

```

## disassembly

```asm
0x1800406b0  push    rbp
0x1800406b2  push    rbx
0x1800406b3  push    rsi
0x1800406b4  push    rdi
0x1800406b5  push    r14
0x1800406b7  lea     rbp, [rsp-1940h]
0x1800406bf  mov     eax, 1A40h
0x1800406c4  call    _alloca_probe
0x1800406c9  sub     rsp, rax
0x1800406cc  mov     rax, cs:__security_cookie
0x1800406d3  xor     rax, rsp
0x1800406d6  mov     [rbp+1960h+var_30], rax
0x1800406dd  mov     [rsp+1A60h+var_1A40], 0
0x1800406e6  mov     edi, r9d
0x1800406e9  mov     [rsp+1A60h+pperrinfo], 0
0x1800406f2  mov     ebx, r8d
0x1800406f5  mov     r14d, edx
0x1800406f8  mov     rsi, rcx
0x1800406fb  cmp     r8d, 64h ; 'd'
0x1800406ff  jnz     short loc_180040708
0x180040701  lock inc cs:?g_nOOMErrors@@3JA; long g_nOOMErrors
0x180040708  lea     rdx, [rsp+1A60h+pperrinfo]; pperrinfo
0x18004070d  xor     ecx, ecx; dwReserved
0x18004070f  call    cs:__imp_GetErrorInfo
0x180040715  test    eax, eax
0x180040717  jnz     short loc_18004072B
0x180040719  mov     rdx, [rsp+1A60h+pperrinfo]; perrinfo
0x18004071e  xor     ecx, ecx; dwReserved
0x180040720  call    cs:__imp_SetErrorInfo
0x180040726  jmp     loc_18004085A
0x18004072b  lea     rcx, [rsp+1A60h+var_1A40]; pperrinfo
0x180040730  call    cs:__imp_CreateErrorInfo
0x180040736  test    eax, eax
0x180040738  js      loc_18004085A
0x18004073e  mov     rcx, [rsp+1A60h+var_1A40]
0x180040743  mov     rdx, rsi
0x180040746  mov     rax, [rcx]
0x180040749  mov     rax, [rax+18h]
0x18004074d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040752  mov     rcx, [rsp+1A60h+var_1A40]
0x180040757  lea     rdx, qword_18006C238
0x18004075e  mov     rax, [rcx]
0x180040761  mov     rax, [rax+30h]
0x180040765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004076a  mov     rcx, [rsp+1A60h+var_1A40]
0x18004076f  xor     edx, edx
0x180040771  mov     rax, [rcx]
0x180040774  mov     rax, [rax+38h]
0x180040778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004077d  mov     esi, 400h
0x180040782  lea     rdx, [rbp+1960h+var_1830]; lpBuffer
0x180040789  mov     r8d, esi; cchBufferMax
0x18004078c  mov     ecx, r14d; uID
0x18004078f  call    ?CwchLoadStringOfId@@YAHIPEAGH@Z; CwchLoadStringOfId(uint,ushort *,int)
0x180040794  test    eax, eax
0x180040796  jz      short loc_1800407B0
0x180040798  mov     rcx, [rsp+1A60h+var_1A40]
0x18004079d  lea     rdx, [rbp+1960h+var_1830]
0x1800407a4  mov     rax, [rcx]
0x1800407a7  mov     rax, [rax+20h]
0x1800407ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407b0  mov     r8d, esi; cchBufferMax
0x1800407b3  lea     rdx, [rbp+1960h+Format]; lpBuffer
0x1800407ba  mov     ecx, ebx; uID
0x1800407bc  call    ?CwchLoadStringOfId@@YAHIPEAGH@Z; CwchLoadStringOfId(uint,ushort *,int)
0x1800407c1  test    eax, eax
0x1800407c3  jz      short loc_18004080B
0x1800407c5  mov     r8d, 100h; SizeInWords
0x1800407cb  lea     rdx, [rsp+1A60h+Destination]; Destination
0x1800407d0  mov     ecx, edi; Value
0x1800407d2  call    ?HResultToWsz@@YAHJPEAGK@Z; HResultToWsz(long,ushort *,ulong)
0x1800407d7  lea     r9, [rsp+1A60h+Destination]
0x1800407dc  mov     rdx, rsi; BufferCount
0x1800407df  lea     r8, [rbp+1960h+Format]; Format
0x1800407e6  lea     rcx, [rbp+1960h+Buffer]; Buffer
0x1800407ed  call    cs:__imp_swprintf_s
0x1800407f3  mov     rcx, [rsp+1A60h+var_1A40]
0x1800407f8  lea     rdx, [rbp+1960h+Buffer]
0x1800407ff  mov     rax, [rcx]
0x180040802  mov     rax, [rax+28h]
0x180040806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004080b  mov     rcx, [rsp+1A60h+var_1A40]
0x180040810  lea     r8, [rsp+1A60h+pperrinfo]
0x180040815  lea     rdx, IID_IErrorInfo
0x18004081c  mov     rax, [rcx]
0x18004081f  mov     rax, [rax]
0x180040822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040827  test    eax, eax
0x180040829  js      short loc_180040849
0x18004082b  mov     rdx, [rsp+1A60h+pperrinfo]; perrinfo
0x180040830  xor     ecx, ecx; dwReserved
0x180040832  call    cs:__imp_SetErrorInfo
0x180040838  mov     rcx, [rsp+1A60h+pperrinfo]
0x18004083d  mov     rax, [rcx]
0x180040840  mov     rax, [rax+10h]
0x180040844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040849  mov     rcx, [rsp+1A60h+var_1A40]
0x18004084e  mov     rax, [rcx]
0x180040851  mov     rax, [rax+10h]
0x180040855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004085a  mov     rcx, [rbp+1960h+var_30]
0x180040861  xor     rcx, rsp; StackCookie
0x180040864  call    __security_check_cookie
0x180040869  add     rsp, 1A40h
0x180040870  pop     r14
0x180040872  pop     rdi
0x180040873  pop     rsi
0x180040874  pop     rbx
0x180040875  pop     rbp
0x180040876  retn
```
