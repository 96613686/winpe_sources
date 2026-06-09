# BdeCfgSecureFormatVolume(IVdsVolume *,IBdeCfgAsync * *)

- ea: `0x180004dfc`
- end: `0x180004f27`
- name: `?BdeCfgSecureFormatVolume@@YAJPEAUIVdsVolume@@PEAPEAVIBdeCfgAsync@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct IVdsVolume *, struct IBdeCfgAsync **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800101a0`

## callees

- `0x1800015c4`
- `0x180004dfc`
- `0x180015010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180004eb4`
- `KERNEL32!CreateThread` at `0x180004eb4`
- `KERNEL32!GetLastError` at `0x180004ec3`
- `KERNEL32!GetLastError` at `0x180004ec3`

## pseudocode

```c
__int64 __fastcall BdeCfgSecureFormatVolume(struct IVdsVolume *a1, struct IBdeCfgAsync **a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = 0;
  if ( g_pService )
  {
    v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( !v5 )
      return (unsigned int)-2147024882;
    v5[3] = 0;
    *v5 = &CBdeCfgSecureFormat::`vftable';
    *((_DWORD *)v5 + 2) = 1;
    v4 = 0;
    *((_DWORD *)v5 + 3) = 0;
    *((_BYTE *)v5 + 16) = 0;
    v5[4] = 0;
    v5[5] = 0;
    v5[6] = 0;
    *((_DWORD *)v5 + 14) = 0;
    ((void (__fastcall *)(struct IVdsVolume *))a1->lpVtbl->AddRef)(a1);
    v6[4] = a1;
    Thread = CreateThread(0, 0, CBdeCfgSecureFormat::WipeAndFormatEntry, v6, 0, 0);
    v6[3] = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (v4 & 0x80000000) == 0 )
    {
      if ( a2 )
      {
        *a2 = (struct IBdeCfgAsync *)v6;
        return v4;
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v6 + 24LL))(v6, &v10);
      if ( v10 < 0 )
        v4 = v10;
    }
    (*(void (__fastcall **)(_QWORD *))(*v6 + 40LL))(v6);
  }
  else
  {
    return (unsigned int)-1063256042;
  }
  return v4;
}

```

## disassembly

```asm
0x180004dfc  push    rbx
0x180004dfe  push    rsi
0x180004dff  push    rdi
0x180004e00  push    r14
0x180004e02  sub     rsp, 38h
0x180004e06  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180004e0e  mov     rsi, rdx
0x180004e11  mov     r14, rcx
0x180004e14  mov     [rsp+58h+arg_10], 0
0x180004e1c  jnz     short loc_180004E28
0x180004e1e  mov     ebx, 0C0A00016h
0x180004e23  jmp     loc_180004F1B
0x180004e28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004e2f  mov     ecx, 40h ; '@'; unsigned __int64
0x180004e34  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004e39  mov     rdi, rax
0x180004e3c  test    rax, rax
0x180004e3f  jz      loc_180004F16
0x180004e45  lea     rax, ??_7CBdeCfgSecureFormat@@6B@; const CBdeCfgSecureFormat::`vftable'
0x180004e4c  mov     qword ptr [rdi+18h], 0
0x180004e54  mov     [rdi], rax
0x180004e57  mov     rcx, r14
0x180004e5a  mov     dword ptr [rdi+8], 1
0x180004e61  xor     ebx, ebx
0x180004e63  mov     dword ptr [rdi+0Ch], 0
0x180004e6a  mov     byte ptr [rdi+10h], 0
0x180004e6e  mov     qword ptr [rdi+20h], 0
0x180004e76  mov     qword ptr [rdi+28h], 0
0x180004e7e  mov     qword ptr [rdi+30h], 0
0x180004e86  mov     dword ptr [rdi+38h], 0
0x180004e8d  mov     rax, [r14]
0x180004e90  mov     rax, [rax+8]
0x180004e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e99  mov     r9, rdi; lpParameter
0x180004e9c  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x180004ea1  lea     r8, ?WipeAndFormatEntry@CBdeCfgSecureFormat@@CAKPEAX@Z; lpStartAddress
0x180004ea8  mov     [rdi+20h], r14
0x180004eac  xor     edx, edx; dwStackSize
0x180004eae  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x180004eb2  xor     ecx, ecx; lpThreadAttributes
0x180004eb4  call    cs:__imp_CreateThread
0x180004eba  mov     [rdi+18h], rax
0x180004ebe  test    rax, rax
0x180004ec1  jnz     short loc_180004ED8
0x180004ec3  call    cs:__imp_GetLastError
0x180004ec9  mov     ebx, eax
0x180004ecb  test    eax, eax
0x180004ecd  jle     short loc_180004ED8
0x180004ecf  movzx   ebx, ax
0x180004ed2  or      ebx, 80070000h
0x180004ed8  test    ebx, ebx
0x180004eda  js      short loc_180004F00
0x180004edc  test    rsi, rsi
0x180004edf  jnz     short loc_180004F11
0x180004ee1  mov     rax, [rdi]
0x180004ee4  lea     rdx, [rsp+58h+arg_10]
0x180004ee9  mov     rcx, rdi
0x180004eec  mov     rax, [rax+18h]
0x180004ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef5  mov     ebx, eax
0x180004ef7  mov     eax, [rsp+58h+arg_10]
0x180004efb  test    eax, eax
0x180004efd  cmovs   ebx, eax
0x180004f00  mov     rax, [rdi]
0x180004f03  mov     rcx, rdi
0x180004f06  mov     rax, [rax+28h]
0x180004f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f0f  jmp     short loc_180004F1B
0x180004f11  mov     [rsi], rdi
0x180004f14  jmp     short loc_180004F1B
0x180004f16  mov     ebx, 8007000Eh
0x180004f1b  mov     eax, ebx
0x180004f1d  add     rsp, 38h
0x180004f21  pop     r14
0x180004f23  pop     rdi
0x180004f24  pop     rsi
0x180004f25  pop     rbx
0x180004f26  retn
```
