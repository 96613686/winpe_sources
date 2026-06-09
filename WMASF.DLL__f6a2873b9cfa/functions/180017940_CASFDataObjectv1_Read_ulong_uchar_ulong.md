# CASFDataObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180017940`
- end: `0x180017a71`
- name: `?Read@CASFDataObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `305`
- prototype: `__int64 __fastcall(CASFDataObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x180017940`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFDataObjectv1::Read(
        CASFDataObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  __int64 result; // rax
  GUID *v7; // rbp
  int v8; // esi
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 3222079478LL;
  if ( !a4 )
    return 2147942487LL;
  if ( !a2 )
  {
LABEL_12:
    *a4 = 50;
    return 3222079441LL;
  }
  if ( !a3 )
    return 2147942487LL;
  if ( a2 < 0x32 )
    goto LABEL_12;
  v7 = (GUID *)((char *)this + 48);
  v8 = 0;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  *(_OWORD *)((char *)this + 316) = *(_OWORD *)(a3 + 24);
  *((_QWORD *)this + 42) = *((_QWORD *)a3 + 5);
  *((_BYTE *)this + 344) = a3[48];
  *((_BYTE *)this + 345) = a3[49];
  *a4 = 50;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v9 )
  {
    v10 = 0;
    v8 = (**v9)(v9, &IID_IASFReadWriteTracker, &v10);
    if ( v8 >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, GUID *))(*(_QWORD *)v10 + 72LL))(v10, a3, *a4, v7);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  result = (unsigned int)v8;
  *v7 = CLSID_ASFDataObject;
  return result;
}

```

## disassembly

```asm
0x180017940  mov     [rsp+arg_8], rbx
0x180017945  push    rbp
0x180017946  push    rsi
0x180017947  push    rdi
0x180017948  sub     rsp, 40h
0x18001794c  mov     rax, cs:__security_cookie
0x180017953  xor     rax, rsp
0x180017956  mov     [rsp+58h+var_20], rax
0x18001795b  cmp     qword ptr [rcx+28h], 0
0x180017960  mov     rbx, r9
0x180017963  mov     rdi, r8
0x180017966  jnz     short loc_180017972
0x180017968  mov     eax, 0C00D07F6h
0x18001796d  jmp     loc_180017A57
0x180017972  test    rbx, rbx
0x180017975  jz      loc_180017A52
0x18001797b  mov     r8d, 32h ; '2'
0x180017981  test    edx, edx
0x180017983  jz      loc_180017A48
0x180017989  test    rdi, rdi
0x18001798c  jz      loc_180017A52
0x180017992  cmp     edx, r8d
0x180017995  jb      loc_180017A48
0x18001799b  movups  xmm0, xmmword ptr [rdi]
0x18001799e  lea     rbp, [rcx+30h]
0x1800179a2  xor     esi, esi
0x1800179a4  movdqu  xmmword ptr [rbp+0], xmm0
0x1800179a9  mov     rax, [rdi+10h]
0x1800179ad  mov     [rcx+40h], rax
0x1800179b1  movups  xmm0, xmmword ptr [rdi+18h]
0x1800179b5  movdqu  xmmword ptr [rcx+13Ch], xmm0
0x1800179bd  mov     rax, [rdi+28h]
0x1800179c1  mov     [rcx+150h], rax
0x1800179c8  mov     al, [rdi+30h]
0x1800179cb  mov     [rcx+158h], al
0x1800179d1  mov     al, [rdi+31h]
0x1800179d4  mov     [rcx+159h], al
0x1800179da  mov     [r9], r8d
0x1800179dd  mov     rcx, [rcx+28h]
0x1800179e1  test    rcx, rcx
0x1800179e4  jz      short loc_180017A38
0x1800179e6  mov     [rsp+58h+var_28], rsi
0x1800179eb  lea     r8, [rsp+58h+var_28]
0x1800179f0  mov     rax, [rcx]
0x1800179f3  lea     rdx, IID_IASFReadWriteTracker
0x1800179fa  mov     rax, [rax]
0x1800179fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a02  mov     esi, eax
0x180017a04  test    eax, eax
0x180017a06  js      short loc_180017A38
0x180017a08  mov     rcx, [rsp+58h+var_28]
0x180017a0d  mov     rdx, rdi
0x180017a10  mov     r8d, [rbx]
0x180017a13  mov     r9, [rcx]
0x180017a16  mov     rax, [r9+48h]
0x180017a1a  mov     r9, rbp
0x180017a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a22  mov     rcx, [rsp+58h+var_28]
0x180017a27  test    rcx, rcx
0x180017a2a  jz      short loc_180017A38
0x180017a2c  mov     rax, [rcx]
0x180017a2f  mov     rax, [rax+10h]
0x180017a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a38  movups  xmm0, xmmword ptr cs:CLSID_ASFDataObject.Data1
0x180017a3f  mov     eax, esi
0x180017a41  movdqu  xmmword ptr [rbp+0], xmm0
0x180017a46  jmp     short loc_180017A57
0x180017a48  mov     [r9], r8d
0x180017a4b  mov     eax, 0C00D07D1h
0x180017a50  jmp     short loc_180017A57
0x180017a52  mov     eax, 80070057h
0x180017a57  mov     rcx, [rsp+58h+var_20]
0x180017a5c  xor     rcx, rsp; StackCookie
0x180017a5f  call    __security_check_cookie
0x180017a64  mov     rbx, [rsp+58h+arg_8]
0x180017a69  add     rsp, 40h
0x180017a6d  pop     rdi
0x180017a6e  pop     rsi
0x180017a6f  pop     rbp
0x180017a70  retn
```
