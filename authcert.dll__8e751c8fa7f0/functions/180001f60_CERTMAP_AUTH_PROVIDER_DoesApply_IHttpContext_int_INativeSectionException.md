# CERTMAP_AUTH_PROVIDER::DoesApply(IHttpContext *,int *,INativeSectionException * *)

- ea: `0x180001f60`
- end: `0x180001feb`
- name: `?DoesApply@CERTMAP_AUTH_PROVIDER@@UEAAJPEAVIHttpContext@@PEAHPEAPEAVINativeSectionException@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(CERTMAP_AUTH_PROVIDER *__hidden this, struct IHttpContext *, int *, struct INativeSectionException **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f60`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CERTMAP_AUTH_PROVIDER::DoesApply(
        CERTMAP_AUTH_PROVIDER *this,
        struct IHttpContext *a2,
        int *a3,
        struct INativeSectionException **a4)
{
  __int64 result; // rax
  __int64 v6; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v7[0] = 0;
  if ( !a3 )
    return 2147942487LL;
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  *a3 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD *, int *))(*(_QWORD *)v6 + 160LL))(v6, v7, &v8);
  if ( (int)result >= 0 )
  {
    *a3 = v7[0] && (unsigned __int64)(*(_QWORD *)(v7[0] + 16LL) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001f60  push    rbx
0x180001f62  sub     rsp, 30h
0x180001f66  mov     [rsp+38h+arg_10], 0
0x180001f6e  mov     rbx, r8
0x180001f71  mov     [rsp+38h+var_18], 0
0x180001f7a  test    r8, r8
0x180001f7d  jnz     short loc_180001F86
0x180001f7f  mov     eax, 80070057h
0x180001f84  jmp     short loc_180001FE5
0x180001f86  mov     rax, [rdx]
0x180001f89  mov     rcx, rdx
0x180001f8c  mov     rax, [rax+18h]
0x180001f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f95  mov     r9, rax
0x180001f98  mov     dword ptr [rbx], 0
0x180001f9e  lea     r8, [rsp+38h+arg_10]
0x180001fa3  lea     rdx, [rsp+38h+var_18]
0x180001fa8  mov     rcx, [rax]
0x180001fab  mov     rax, [rcx+0A0h]
0x180001fb2  mov     rcx, r9
0x180001fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fba  test    eax, eax
0x180001fbc  js      short loc_180001FE5
0x180001fbe  mov     rax, [rsp+38h+var_18]
0x180001fc3  test    rax, rax
0x180001fc6  jz      short loc_180001FDD
0x180001fc8  mov     rax, [rax+10h]
0x180001fcc  dec     rax
0x180001fcf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001fd3  ja      short loc_180001FDD
0x180001fd5  mov     dword ptr [rbx], 1
0x180001fdb  jmp     short loc_180001FE3
0x180001fdd  mov     dword ptr [rbx], 0
0x180001fe3  xor     eax, eax
0x180001fe5  add     rsp, 30h
0x180001fe9  pop     rbx
0x180001fea  retn
```
