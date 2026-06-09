# IIS_CRYPTO_STORAGE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int)

- ea: `0x180005900`
- end: `0x180005982`
- name: `?Initialize@IIS_CRYPTO_STORAGE@@QEAAJ_K000H@Z`
- size: `130`
- prototype: `__int64 __fastcall(IIS_CRYPTO_STORAGE *__hidden this, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003538`
- `0x180003b9c`

## callees

- `0x1800053bc`
- `0x180005900`
- `0x180007234`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_STORAGE::Initialize(
        IIS_CRYPTO_STORAGE *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6)
{
  int v8; // ebx

  v8 = IIS_CRYPTO_BASE::Initialize((IIS_CRYPTO_STORAGE *)((char *)this + 8), a2, a3, a5, a6);
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\storage.cxx",
        460,
        "IIS_CRYPTO_STORAGE::Initialize",
        "IIS_CRYPTO_STORAGE::Initialize IIS_CRYPTO_BASE::Initialize failed err=0x%x.\n",
        v8);
  }
  else
  {
    *((_QWORD *)this + 5) = a3;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005900  mov     [rsp+arg_0], rbx
0x180005905  mov     [rsp+arg_8], rsi
0x18000590a  push    rdi
0x18000590b  sub     rsp, 30h
0x18000590f  mov     eax, [rsp+38h+arg_28]
0x180005913  mov     rdi, rcx
0x180005916  mov     r9, [rsp+38h+arg_20]; unsigned __int64
0x18000591b  add     rcx, 8; this
0x18000591f  mov     rsi, r8
0x180005922  mov     dword ptr [rsp+38h+var_18], eax; int
0x180005926  call    ?Initialize@IIS_CRYPTO_BASE@@QEAAJ_K00H@Z; IIS_CRYPTO_BASE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,int)
0x18000592b  mov     ebx, eax
0x18000592d  test    eax, eax
0x18000592f  js      short loc_180005937
0x180005931  mov     [rdi+28h], rsi
0x180005935  jmp     short loc_180005970
0x180005937  test    byte ptr cs:g_dwDebugFlags, 3
0x18000593e  jz      short loc_180005970
0x180005940  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005947  lea     rax, aIisCryptoStora; "IIS_CRYPTO_STORAGE::Initialize IIS_CRYP"...
0x18000594e  mov     dword ptr [rsp+38h+var_10], ebx; char
0x180005952  lea     r9, aIisCryptoStora_0; "IIS_CRYPTO_STORAGE::Initialize"
0x180005959  mov     r8d, 1CCh; unsigned int
0x18000595f  mov     [rsp+38h+var_18], rax; char *
0x180005964  lea     rdx, aInetsrvIisMbCr_0; "inetsrv\\iis\\mb\\crypto\\storage.cxx"
0x18000596b  call    PuDbgPrint
0x180005970  mov     rsi, [rsp+38h+arg_8]
0x180005975  mov     eax, ebx
0x180005977  mov     rbx, [rsp+38h+arg_0]
0x18000597c  add     rsp, 30h
0x180005980  pop     rdi
0x180005981  retn
```
