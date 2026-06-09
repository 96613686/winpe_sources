# PimIMService::GetCustomEvent(TransactionData const *,PIMCUSTOMEVENT *)

- ea: `0x180006e30`
- end: `0x180006f41`
- name: `?GetCustomEvent@PimIMService@@UEAAJPEBUTransactionData@@PEAUPIMCUSTOMEVENT@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, const struct TransactionData *, struct PIMCUSTOMEVENT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180006e30`
- `0x1800086a0`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f16`

## string_xrefs

- `0x180006e73`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180006e8a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetCustomEvent(
        PimIMService *this,
        const struct TransactionData *a2,
        struct PIMCUSTOMEVENT *a3)
{
  char *v6; // rax
  char *v7; // rsi
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // edx
  __int16 v11; // r8
  __int16 v12; // r9
  _BYTE v14[16]; // [rsp+48h] [rbp-30h] BYREF

  if ( !a2 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2671);
  if ( !a3 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2672);
  v6 = (char *)LocalAlloc(0x40u, 0xCu);
  v7 = v6;
  if ( v6 )
  {
    *(_DWORD *)v6 = *(_DWORD *)a2;
    v8 = 0;
    *(_QWORD *)(v6 + 4) = *((_QWORD *)a2 + 2);
    v9 = (*(__int64 (__fastcall **)(PimIMService *, _BYTE *))(*(_QWORD *)this + 208LL))(this, v14);
    v10 = *(_DWORD *)v9;
    v11 = *(_WORD *)(v9 + 4);
    v12 = *(_WORD *)(v9 + 6);
    *((_QWORD *)a3 + 1) = *(_QWORD *)(v9 + 8);
    *((_DWORD *)a3 + 5) = 0;
    *((_QWORD *)a3 + 4) = 0;
    *(_DWORD *)a3 = v10;
    *((_WORD *)a3 + 2) = v11;
    *((_WORD *)a3 + 3) = v12;
    *((_DWORD *)a3 + 4) = 12;
    *((_QWORD *)a3 + 3) = v7;
  }
  else
  {
    v8 = -2147024882;
  }
  LocalFree(0);
  return v8;
}

```

## disassembly

```asm
0x180006e30  mov     [rsp+arg_8], rbx
0x180006e35  mov     [rsp+arg_18], rsi
0x180006e3a  push    rdi
0x180006e3b  push    r14
0x180006e3d  push    r15
0x180006e3f  sub     rsp, 60h
0x180006e43  mov     rax, cs:__security_cookie
0x180006e4a  xor     rax, rsp
0x180006e4d  mov     [rsp+78h+var_20], rax
0x180006e52  xorps   xmm0, xmm0
0x180006e55  mov     rbx, r8
0x180006e58  mov     r14, rdx
0x180006e5b  mov     r15, rcx
0x180006e5e  movups  [rsp+78h+var_50], xmm0
0x180006e63  movups  [rsp+78h+var_40], xmm0
0x180006e68  test    rdx, rdx
0x180006e6b  jnz     short loc_180006E7F
0x180006e6d  mov     r8d, 0A6Fh
0x180006e73  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006e7a  call    Log_AssertionEvent
0x180006e7f  test    rbx, rbx
0x180006e82  jnz     short loc_180006E96
0x180006e84  mov     r8d, 0A70h
0x180006e8a  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006e91  call    Log_AssertionEvent
0x180006e96  mov     edx, 0Ch; uBytes
0x180006e9b  lea     ecx, [rdx+34h]; uFlags
0x180006e9e  call    cs:__imp_LocalAlloc
0x180006ea4  mov     rsi, rax
0x180006ea7  test    rax, rax
0x180006eaa  jnz     short loc_180006EB3
0x180006eac  mov     edi, 8007000Eh
0x180006eb1  jmp     short loc_180006F14
0x180006eb3  mov     eax, [r14]
0x180006eb6  lea     rdx, [rsp+78h+var_30]
0x180006ebb  mov     [rsi], eax
0x180006ebd  xor     edi, edi
0x180006ebf  mov     rax, [r14+10h]
0x180006ec3  mov     rcx, r15
0x180006ec6  mov     [rsi+4], rax
0x180006eca  mov     rax, [r15]
0x180006ecd  mov     rax, [rax+0D0h]
0x180006ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed9  mov     rcx, [rax+8]
0x180006edd  mov     edx, [rax]
0x180006edf  movzx   r8d, word ptr [rax+4]
0x180006ee4  movzx   r9d, word ptr [rax+6]
0x180006ee9  mov     [rbx+8], rcx
0x180006eed  mov     ecx, dword ptr [rsp+78h+var_50+0Ch]
0x180006ef1  mov     [rbx+14h], ecx
0x180006ef4  mov     rcx, qword ptr [rsp+78h+var_40+8]
0x180006ef9  mov     [rbx+20h], rcx
0x180006efd  mov     [rbx], edx
0x180006eff  mov     [rbx+4], r8w
0x180006f04  mov     [rbx+6], r9w
0x180006f09  mov     dword ptr [rbx+10h], 0Ch
0x180006f10  mov     [rbx+18h], rsi
0x180006f14  xor     ecx, ecx; hMem
0x180006f16  call    cs:__imp_LocalFree
0x180006f1c  mov     eax, edi
0x180006f1e  mov     rcx, [rsp+78h+var_20]
0x180006f23  xor     rcx, rsp; StackCookie
0x180006f26  call    __security_check_cookie
0x180006f2b  lea     r11, [rsp+78h+var_18]
0x180006f30  mov     rbx, [r11+28h]
0x180006f34  mov     rsi, [r11+38h]
0x180006f38  mov     rsp, r11
0x180006f3b  pop     r15
0x180006f3d  pop     r14
0x180006f3f  pop     rdi
0x180006f40  retn
```
