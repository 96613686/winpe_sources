# CSyncChangeWrapper::ConvertToLocalDelete(IAsynchronousNotifyingChangeApplierTarget *,unsigned __int64 *)

- ea: `0x180067b24`
- end: `0x180067c2c`
- name: `?ConvertToLocalDelete@CSyncChangeWrapper@@QEAAJPEAUIAsynchronousNotifyingChangeApplierTarget@@PEA_K@Z`
- size: `264`
- prototype: `__int64 __fastcall(CSyncChangeWrapper *__hidden this, struct IAsynchronousNotifyingChangeApplierTarget *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180033cec`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180067b24`
- `0x180094010`

## string_xrefs

- `0x180067b5d`: `CSyncChangeWrapper::ConvertToLocalDelete`
- `0x180067c01`: `CSyncChangeWrapper::ConvertToLocalDelete`

## pseudocode

```c
__int64 __fastcall CSyncChangeWrapper::ConvertToLocalDelete(
        CSyncChangeWrapper *this,
        struct IAsynchronousNotifyingChangeApplierTarget *a2,
        unsigned __int64 *a3)
{
  PVOID *v6; // rcx
  int v7; // edi
  __int64 v8; // rcx
  unsigned __int64 v9; // rax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      159,
      WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      "CSyncChangeWrapper::ConvertToLocalDelete");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = -2147467261;
  if ( a2 && a3 )
  {
    v7 = (*(__int64 (__fastcall **)(struct IAsynchronousNotifyingChangeApplierTarget *, char *))(*(_QWORD *)a2 + 56LL))(
           a2,
           (char *)this + 256);
    if ( v7 >= 0 )
    {
      v8 = *((_QWORD *)this + 25);
      if ( v8 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        *((_QWORD *)this + 25) = 0;
      }
      v9 = *((_QWORD *)this + 32);
      *((_DWORD *)this + 42) |= 1u;
      *((_QWORD *)this + 15) = v9;
      *a3 = v9;
      *((_DWORD *)this + 28) = 0;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      160,
      (unsigned int)WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids,
      (unsigned int)"CSyncChangeWrapper::ConvertToLocalDelete",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067b24  push    rbx
0x180067b26  push    rbp
0x180067b27  push    rsi
0x180067b28  push    rdi
0x180067b29  push    r14
0x180067b2b  push    r15
0x180067b2d  sub     rsp, 38h
0x180067b31  mov     r14, r8
0x180067b34  mov     rsi, rdx
0x180067b37  mov     rbx, rcx
0x180067b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b41  lea     rbp, WPP_GLOBAL_Control
0x180067b48  cmp     rcx, rbp
0x180067b4b  jz      short loc_180067B7C
0x180067b4d  test    byte ptr [rcx+1Ch], 8
0x180067b51  jz      short loc_180067B7C
0x180067b53  cmp     byte ptr [rcx+19h], 5
0x180067b57  jb      short loc_180067B7C
0x180067b59  mov     rcx, [rcx+10h]
0x180067b5d  lea     r9, aCsyncchangewra_72; "CSyncChangeWrapper::ConvertToLocalDelet"...
0x180067b64  mov     edx, 9Fh
0x180067b69  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180067b70  call    WPP_SF_s
0x180067b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180067b7c  mov     edi, 80004003h
0x180067b81  test    rsi, rsi
0x180067b84  jz      short loc_180067BEC
0x180067b86  test    r14, r14
0x180067b89  jz      short loc_180067BEC
0x180067b8b  mov     rax, [rsi]
0x180067b8e  lea     r15, [rbx+100h]
0x180067b95  mov     rdx, r15
0x180067b98  mov     rcx, rsi
0x180067b9b  mov     rax, [rax+38h]
0x180067b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ba4  mov     edi, eax
0x180067ba6  test    eax, eax
0x180067ba8  js      short loc_180067BE5
0x180067baa  mov     rcx, [rbx+0C8h]
0x180067bb1  test    rcx, rcx
0x180067bb4  jz      short loc_180067BCD
0x180067bb6  mov     rdx, [rcx]
0x180067bb9  mov     rax, [rdx+10h]
0x180067bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067bc2  mov     qword ptr [rbx+0C8h], 0
0x180067bcd  mov     rax, [r15]
0x180067bd0  or      dword ptr [rbx+0A8h], 1
0x180067bd7  mov     [rbx+78h], rax
0x180067bdb  mov     [r14], rax
0x180067bde  mov     dword ptr [rbx+70h], 0
0x180067be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180067bec  cmp     rcx, rbp
0x180067bef  jz      short loc_180067C1D
0x180067bf1  test    byte ptr [rcx+1Ch], 8
0x180067bf5  jz      short loc_180067C1D
0x180067bf7  cmp     byte ptr [rcx+19h], 5
0x180067bfb  jb      short loc_180067C1D
0x180067bfd  mov     rcx, [rcx+10h]
0x180067c01  lea     r9, aCsyncchangewra_72; "CSyncChangeWrapper::ConvertToLocalDelet"...
0x180067c08  mov     edx, 0A0h
0x180067c0d  mov     [rsp+68h+var_48], edi
0x180067c11  lea     r8, WPP_1ce7e5fbf03e39cbecdc9dc9cb74efd7_Traceguids
0x180067c18  call    WPP_SF_sD
0x180067c1d  mov     eax, edi
0x180067c1f  add     rsp, 38h
0x180067c23  pop     r15
0x180067c25  pop     r14
0x180067c27  pop     rdi
0x180067c28  pop     rsi
0x180067c29  pop     rbp
0x180067c2a  pop     rbx
0x180067c2b  retn
```
