# CPimcContext::GetCommHandle(__int64 *)

- ea: `0x180006ba4`
- end: `0x180006c94`
- name: `?GetCommHandle@CPimcContext@@QEAAJPEA_J@Z`
- size: `240`
- prototype: `__int64 __fastcall(CPimcContext *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800082f0`

## callees

- `0x180001190`
- `0x180001240`
- `0x180006ba4`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall CPimcContext::GetCommHandle(CPimcContext *this, __int64 *a2)
{
  __int64 result; // rax
  _OWORD *v4; // rax
  __int64 v5; // xmm1_8
  __m128d *v6; // rax
  __m128d v7; // xmm1
  void (__fastcall *v8)(CPimcContext *); // rax
  _BYTE v9[16]; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v10[2]; // [rsp+30h] [rbp-28h]

  result = a2 == 0 ? 0x80070057 : 0;
  if ( a2 )
  {
    if ( *((_DWORD *)this + 74) )
    {
      result = *((_DWORD *)this + 28) != 0 ? 0x8000FFFF : 0;
      if ( !*((_DWORD *)this + 28) )
      {
        *((_DWORD *)this + 28) = 1;
        *a2 = (__int64)this;
        v4 = (_OWORD *)ComUtils::ComApartmentVerifier::CurrentSta((__int64)v9);
        *(_QWORD *)&v10[0] = this;
        *(_OWORD *)((char *)v10 + 8) = *v4;
        v5 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)((char *)v10 + 8), *(__m128d *)((char *)v10 + 8));
        *(_OWORD *)((char *)this + 248) = v10[0];
        *((_QWORD *)this + 33) = v5;
        v6 = (__m128d *)ComUtils::ComApartmentVerifier::CurrentSta((__int64)v9);
        *(_QWORD *)&v10[0] = *((_QWORD *)this + 2);
        v7 = *v6;
        v8 = *(void (__fastcall **)(CPimcContext *))(*(_QWORD *)this + 8LL);
        *(__m128d *)((char *)v10 + 8) = v7;
        *((_OWORD *)this + 17) = v10[0];
        *((_QWORD *)this + 36) = *(_OWORD *)&_mm_unpackhi_pd(v7, v7);
        v8(this);
        result = ComUtils::ComLockableWrapper::Lock((CPimcContext *)((char *)this + 248));
        if ( (int)result >= 0 )
          return ComUtils::ComLockableWrapper::Lock((CPimcContext *)((char *)this + 272));
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006ba4  mov     [rsp+arg_0], rbx
0x180006ba9  mov     [rsp+arg_8], rsi
0x180006bae  push    rdi
0x180006baf  sub     rsp, 50h
0x180006bb3  mov     rax, rdx
0x180006bb6  mov     rdi, rcx
0x180006bb9  neg     rax
0x180006bbc  sbb     eax, eax
0x180006bbe  not     eax
0x180006bc0  and     eax, 80070057h
0x180006bc5  test    rdx, rdx
0x180006bc8  jz      loc_180006C84
0x180006bce  cmp     dword ptr [rcx+128h], 0
0x180006bd5  jz      loc_180006C84
0x180006bdb  mov     eax, [rcx+70h]
0x180006bde  neg     eax
0x180006be0  sbb     eax, eax
0x180006be2  and     eax, 8000FFFFh
0x180006be7  cmp     dword ptr [rcx+70h], 0
0x180006beb  jnz     loc_180006C84
0x180006bf1  mov     dword ptr [rcx+70h], 1
0x180006bf8  mov     [rdx], rcx
0x180006bfb  lea     rcx, [rsp+58h+var_38]
0x180006c00  call    ?CurrentSta@ComApartmentVerifier@ComUtils@@SA?AV12@XZ; ComUtils::ComApartmentVerifier::CurrentSta(void)
0x180006c05  lea     rbx, [rdi+0F8h]
0x180006c0c  mov     qword ptr [rsp+58h+var_28], rdi
0x180006c11  lea     rcx, [rsp+58h+var_38]
0x180006c16  movups  xmm1, xmmword ptr [rax]
0x180006c19  movups  xmmword ptr [rsp+58h+var_28+8], xmm1
0x180006c1e  movups  xmm0, xmmword ptr [rsp+58h+var_28]
0x180006c23  unpckhpd xmm1, xmm1
0x180006c27  movups  xmmword ptr [rbx], xmm0
0x180006c2a  movsd   qword ptr [rbx+10h], xmm1
0x180006c2f  call    ?CurrentSta@ComApartmentVerifier@ComUtils@@SA?AV12@XZ; ComUtils::ComApartmentVerifier::CurrentSta(void)
0x180006c34  mov     rcx, rax
0x180006c37  lea     rsi, [rdi+110h]
0x180006c3e  mov     rax, [rdi+10h]
0x180006c42  mov     qword ptr [rsp+58h+var_28], rax
0x180006c47  mov     rax, [rdi]
0x180006c4a  movups  xmm1, xmmword ptr [rcx]
0x180006c4d  mov     rcx, rdi
0x180006c50  mov     rax, [rax+8]
0x180006c54  movups  xmmword ptr [rsp+58h+var_28+8], xmm1
0x180006c59  movups  xmm0, xmmword ptr [rsp+58h+var_28]
0x180006c5e  unpckhpd xmm1, xmm1
0x180006c62  movups  xmmword ptr [rsi], xmm0
0x180006c65  movsd   qword ptr [rsi+10h], xmm1
0x180006c6a  call    cs:__guard_dispatch_icall_fptr
0x180006c70  mov     rcx, rbx; this
0x180006c73  call    ?Lock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Lock(void)
0x180006c78  test    eax, eax
0x180006c7a  js      short loc_180006C84
0x180006c7c  mov     rcx, rsi; this
0x180006c7f  call    ?Lock@ComLockableWrapper@ComUtils@@QEAAJXZ; ComUtils::ComLockableWrapper::Lock(void)
0x180006c84  mov     rbx, [rsp+58h+arg_0]
0x180006c89  mov     rsi, [rsp+58h+arg_8]
0x180006c8e  add     rsp, 50h
0x180006c92  pop     rdi
0x180006c93  retn
```
