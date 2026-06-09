# BdeCfgSecureFormatPartition(IVdsDisk *,unsigned __int64,IBdeCfgAsync * *)

- ea: `0x180004cb0`
- end: `0x180004df3`
- name: `?BdeCfgSecureFormatPartition@@YAJPEAUIVdsDisk@@_KPEAPEAVIBdeCfgAsync@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(struct IVdsDisk *, __int64, struct IBdeCfgAsync **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800015c4`
- `0x180004cb0`
- `0x180015010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180004d77`
- `KERNEL32!CreateThread` at `0x180004d77`
- `KERNEL32!GetLastError` at `0x180004d86`
- `KERNEL32!GetLastError` at `0x180004d86`

## pseudocode

```c
__int64 __fastcall BdeCfgSecureFormatPartition(struct IVdsDisk *a1, __int64 a2, struct IBdeCfgAsync **a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  if ( g_pService )
  {
    v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    v7[3] = 0;
    *v7 = &CBdeCfgSecureFormat::`vftable';
    *((_DWORD *)v7 + 2) = 1;
    v6 = 0;
    *((_DWORD *)v7 + 3) = 0;
    *((_BYTE *)v7 + 16) = 0;
    v7[4] = 0;
    v7[5] = 0;
    v7[6] = 0;
    *((_DWORD *)v7 + 14) = 0;
    ((void (__fastcall *)(struct IVdsDisk *))a1->lpVtbl->AddRef)(a1);
    v8[5] = a1;
    v8[6] = a2;
    Thread = CreateThread(0, 0, CBdeCfgSecureFormat::WipeAndFormatEntry, v8, 0, 0);
    v8[3] = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (v6 & 0x80000000) == 0 )
    {
      if ( a3 )
      {
        *a3 = (struct IBdeCfgAsync *)v8;
        return v6;
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v8 + 24LL))(v8, &v12);
      if ( v12 < 0 )
        v6 = v12;
    }
    (*(void (__fastcall **)(_QWORD *))(*v8 + 40LL))(v8);
  }
  else
  {
    return (unsigned int)-1063256042;
  }
  return v6;
}

```

## disassembly

```asm
0x180004cb0  mov     [rsp+arg_0], rbx
0x180004cb5  mov     [rsp+arg_8], rbp
0x180004cba  push    rsi
0x180004cbb  push    rdi
0x180004cbc  push    r14
0x180004cbe  sub     rsp, 30h
0x180004cc2  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180004cca  mov     rsi, r8
0x180004ccd  mov     rbp, rdx
0x180004cd0  mov     [rsp+48h+arg_18], 0
0x180004cd8  mov     r14, rcx
0x180004cdb  jnz     short loc_180004CE7
0x180004cdd  mov     ebx, 0C0A00016h
0x180004ce2  jmp     loc_180004DDE
0x180004ce7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004cee  mov     ecx, 40h ; '@'; unsigned __int64
0x180004cf3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004cf8  mov     rdi, rax
0x180004cfb  test    rax, rax
0x180004cfe  jz      loc_180004DD9
0x180004d04  lea     rax, ??_7CBdeCfgSecureFormat@@6B@; const CBdeCfgSecureFormat::`vftable'
0x180004d0b  mov     qword ptr [rdi+18h], 0
0x180004d13  mov     [rdi], rax
0x180004d16  mov     rcx, r14
0x180004d19  mov     dword ptr [rdi+8], 1
0x180004d20  xor     ebx, ebx
0x180004d22  mov     dword ptr [rdi+0Ch], 0
0x180004d29  mov     byte ptr [rdi+10h], 0
0x180004d2d  mov     qword ptr [rdi+20h], 0
0x180004d35  mov     qword ptr [rdi+28h], 0
0x180004d3d  mov     qword ptr [rdi+30h], 0
0x180004d45  mov     dword ptr [rdi+38h], 0
0x180004d4c  mov     rax, [r14]
0x180004d4f  mov     rax, [rax+8]
0x180004d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d58  mov     r9, rdi; lpParameter
0x180004d5b  mov     [rsp+48h+lpThreadId], rbx; lpThreadId
0x180004d60  lea     r8, ?WipeAndFormatEntry@CBdeCfgSecureFormat@@CAKPEAX@Z; lpStartAddress
0x180004d67  mov     [rdi+28h], r14
0x180004d6b  xor     edx, edx; dwStackSize
0x180004d6d  mov     [rdi+30h], rbp
0x180004d71  xor     ecx, ecx; lpThreadAttributes
0x180004d73  mov     [rsp+48h+dwCreationFlags], ebx; dwCreationFlags
0x180004d77  call    cs:__imp_CreateThread
0x180004d7d  mov     [rdi+18h], rax
0x180004d81  test    rax, rax
0x180004d84  jnz     short loc_180004D9B
0x180004d86  call    cs:__imp_GetLastError
0x180004d8c  mov     ebx, eax
0x180004d8e  test    eax, eax
0x180004d90  jle     short loc_180004D9B
0x180004d92  movzx   ebx, ax
0x180004d95  or      ebx, 80070000h
0x180004d9b  test    ebx, ebx
0x180004d9d  js      short loc_180004DC3
0x180004d9f  test    rsi, rsi
0x180004da2  jnz     short loc_180004DD4
0x180004da4  mov     rax, [rdi]
0x180004da7  lea     rdx, [rsp+48h+arg_18]
0x180004dac  mov     rcx, rdi
0x180004daf  mov     rax, [rax+18h]
0x180004db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db8  mov     ebx, eax
0x180004dba  mov     eax, [rsp+48h+arg_18]
0x180004dbe  test    eax, eax
0x180004dc0  cmovs   ebx, eax
0x180004dc3  mov     rax, [rdi]
0x180004dc6  mov     rcx, rdi
0x180004dc9  mov     rax, [rax+28h]
0x180004dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd2  jmp     short loc_180004DDE
0x180004dd4  mov     [rsi], rdi
0x180004dd7  jmp     short loc_180004DDE
0x180004dd9  mov     ebx, 8007000Eh
0x180004dde  mov     rbp, [rsp+48h+arg_8]
0x180004de3  mov     eax, ebx
0x180004de5  mov     rbx, [rsp+48h+arg_0]
0x180004dea  add     rsp, 30h
0x180004dee  pop     r14
0x180004df0  pop     rdi
0x180004df1  pop     rsi
0x180004df2  retn
```
