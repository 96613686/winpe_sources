# BdeCfgGetDeviceNameFromVolume(IVdsVolume *,unsigned __int64,ushort *)

- ea: `0x180004170`
- end: `0x180004207`
- name: `?BdeCfgGetDeviceNameFromVolume@@YAJPEAUIVdsVolume@@_KPEAG@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000202c`
- `0x180003580`
- `0x180006860`
- `0x1800101a0`
- `0x180010800`

## callees

- `0x180004170`
- `0x180006bbc`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800041ea`
- `ole32!CoTaskMemFree` at `0x1800041ea`

## pseudocode

```c
__int64 __fastcall BdeCfgGetDeviceNameFromVolume(struct IVdsVolume *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  int v5; // ebx
  _OWORD v7[3]; // [rsp+20h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-28h]

  pv = 0;
  memset(v7, 0, sizeof(v7));
  if ( a1 && a3 )
  {
    v5 = ((__int64 (__fastcall *)(struct IVdsVolume *, _OWORD *))a1->lpVtbl->GetProperties)(a1, v7);
    if ( v5 >= 0 )
      v5 = StringCchCopyW(a3, a2, (const unsigned __int16 *)pv);
  }
  else
  {
    v5 = -2147467261;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004170  push    rbx
0x180004172  push    rsi
0x180004173  push    rdi
0x180004174  sub     rsp, 60h
0x180004178  mov     rax, cs:__security_cookie
0x18000417f  xor     rax, rsp
0x180004182  mov     [rsp+78h+var_20], rax
0x180004187  xorps   xmm0, xmm0
0x18000418a  xor     eax, eax
0x18000418c  mov     [rsp+78h+pv], rax
0x180004191  mov     rdi, r8
0x180004194  mov     rsi, rdx
0x180004197  movups  [rsp+78h+var_58], xmm0
0x18000419c  movups  [rsp+78h+var_48], xmm0
0x1800041a1  movups  [rsp+78h+var_38], xmm0
0x1800041a6  test    rcx, rcx
0x1800041a9  jz      short loc_1800041DB
0x1800041ab  test    r8, r8
0x1800041ae  jz      short loc_1800041DB
0x1800041b0  mov     rax, [rcx]
0x1800041b3  lea     rdx, [rsp+78h+var_58]
0x1800041b8  mov     rax, [rax+18h]
0x1800041bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c1  mov     ebx, eax
0x1800041c3  test    eax, eax
0x1800041c5  js      short loc_1800041E0
0x1800041c7  mov     r8, [rsp+78h+pv]; unsigned __int16 *
0x1800041cc  mov     rdx, rsi; unsigned __int64
0x1800041cf  mov     rcx, rdi; unsigned __int16 *
0x1800041d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800041d7  mov     ebx, eax
0x1800041d9  jmp     short loc_1800041E0
0x1800041db  mov     ebx, 80004003h
0x1800041e0  mov     rcx, [rsp+78h+pv]; pv
0x1800041e5  test    rcx, rcx
0x1800041e8  jz      short loc_1800041F0
0x1800041ea  call    cs:__imp_CoTaskMemFree
0x1800041f0  mov     eax, ebx
0x1800041f2  mov     rcx, [rsp+78h+var_20]
0x1800041f7  xor     rcx, rsp; StackCookie
0x1800041fa  call    __security_check_cookie
0x1800041ff  add     rsp, 60h
0x180004203  pop     rdi
0x180004204  pop     rsi
0x180004205  pop     rbx
0x180004206  retn
```
