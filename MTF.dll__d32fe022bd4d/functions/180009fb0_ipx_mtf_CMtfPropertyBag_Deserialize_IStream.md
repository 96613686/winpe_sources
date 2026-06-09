# ipx::mtf::CMtfPropertyBag::Deserialize(IStream *)

- ea: `0x180009fb0`
- end: `0x18000a2a9`
- name: `?Deserialize@CMtfPropertyBag@mtf@ipx@@UEAAJPEAUIStream@@@Z`
- size: `761`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfPropertyBag *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180009dc0`
- `0x180009fb0`
- `0x18000a440`
- `0x18002bca0`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ipx::mtf::CMtfPropertyBag::Deserialize(
        ipx::mtf::CMtfPropertyBag *this,
        struct IStream *a2,
        __int64 a3,
        const char *a4)
{
  signed int v6; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 *v11; // rax
  unsigned __int8 *v12; // rcx
  __int64 result; // rax
  int v14; // [rsp+30h] [rbp-48h] BYREF
  int v15; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 *v17; // [rsp+40h] [rbp-38h] BYREF
  __int128 v18; // [rsp+48h] [rbp-30h] BYREF
  struct _GUID v19; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v6 = a2 == 0 ? 0x80070057 : 0;
  try
  {
LABEL_2:
    while ( v6 >= 0 )
    {
      v19 = GUID_NULL;
      v17 = 0;
      v16 = 0;
      v15 = 0;
      LOBYTE(v14) = 0;
      v6 = (*(__int64 (__fastcall **)(struct IStream *, int *, __int64, int *))(*(_QWORD *)a2 + 24LL))(
             a2,
             &v14,
             1,
             &v15);
      if ( v15 != 1 )
        FailFastWithHR(v7, (unsigned __int64)retaddr, 0x232u);
      LOBYTE(v7) = v14;
      if ( !(_BYTE)v14 )
        break;
      if ( (unsigned __int8)(v14 - 1) > 1u )
      {
        FailFastWithHR(v7, (unsigned __int64)retaddr, 0x235u);
        LOBYTE(v7) = v14;
      }
      if ( !(_BYTE)v7 )
        break;
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct IStream *, struct _GUID *, __int64, int *))(*(_QWORD *)a2 + 24LL))(
               a2,
               &v19,
               16,
               &v15);
        LOBYTE(v7) = v14;
      }
      if ( (_BYTE)v7 == 1 )
      {
        if ( v6 < 0 )
          break;
        v6 = (*(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64, int *))(*(_QWORD *)a2 + 24LL))(
               a2,
               &v16,
               4,
               &v15);
        if ( v15 != 4 )
          FailFastWithHR(v8, (unsigned __int64)retaddr, 0x249u);
        if ( v6 < 0 )
          break;
        v6 = ipx::mtf::CMtfPropertyBag::AllocateBufferForValue(
               (ipx::mtf::CMtfPropertyBag *)((char *)this - 8),
               &v19,
               v16,
               &v17);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int8 *, _QWORD, int *))(*(_QWORD *)a2 + 24LL))(
                 a2,
                 v17,
                 v16,
                 &v15);
          if ( v15 != v16 )
            FailFastWithHR(v9, (unsigned __int64)retaddr, 0x256u);
        }
      }
      else
      {
        v18 = 0;
        if ( v6 < 0 )
          break;
        v6 = (*(__int64 (__fastcall **)(struct IStream *, __int128 *, __int64, int *))(*(_QWORD *)a2 + 24LL))(
               a2,
               &v18,
               16,
               &v15);
        if ( v15 != 16 )
          FailFastWithHR(v10, (unsigned __int64)retaddr, 0x260u);
        if ( v6 < 0 )
          break;
        v11 = qword_18003E5D0;
        while ( *(_OWORD *)v11 != v18 )
        {
          v11 += 2;
          if ( v11 == qword_18003F210 )
          {
            v6 = -2147024809;
            goto LABEL_2;
          }
        }
        v17 = 0;
        v6 = ((__int64 (__fastcall *)(__int128 *, _QWORD, __int64, GUID *, unsigned __int8 **))Hooked_CoCreateInstance)(
               &v18,
               0,
               1,
               &GUID_06445657_3a07_492d_94c3_052034ef2d12,
               &v17);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(unsigned __int8 *, struct IStream *))(*(_QWORD *)v17 + 40LL))(v17, a2);
          if ( v6 >= 0 )
            v6 = (*(__int64 (__fastcall **)(char *, struct _GUID *, unsigned __int8 *))(*((_QWORD *)this - 1) + 48LL))(
                   (char *)this - 8,
                   &v19,
                   v17);
        }
        v12 = v17;
        v17 = 0;
        if ( v12 )
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    result = (unsigned int)v6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x288,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\propertybag.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180009fb0  mov     [rsp+arg_10], rbx
0x180009fb5  mov     [rsp+arg_18], rsi
0x180009fba  push    rdi
0x180009fbb  sub     rsp, 70h
0x180009fbf  mov     rax, cs:__security_cookie
0x180009fc6  xor     rax, rsp
0x180009fc9  mov     [rsp+78h+var_10], rax
0x180009fce  mov     rdi, rdx
0x180009fd1  mov     rsi, rcx
0x180009fd4  mov     rax, rdx
0x180009fd7  neg     rax
0x180009fda  sbb     ebx, ebx
0x180009fdc  not     ebx
0x180009fde  and     ebx, 80070057h
0x180009fe4  test    ebx, ebx
0x180009fe6  js      loc_18000A281
0x180009fec  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180009ff3  movdqu  xmmword ptr [rsp+78h+var_20.Data1], xmm0
0x180009ff9  mov     [rsp+78h+var_38], 0
0x18000a002  mov     [rsp+78h+var_40], 0
0x18000a00a  mov     [rsp+78h+var_44], 0
0x18000a012  mov     byte ptr [rsp+78h+var_48], 0
0x18000a017  mov     rax, [rdi]
0x18000a01a  lea     r9, [rsp+78h+var_44]
0x18000a01f  mov     r8d, 1
0x18000a025  lea     rdx, [rsp+78h+var_48]
0x18000a02a  mov     rcx, rdi
0x18000a02d  mov     rax, [rax+18h]
0x18000a031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a036  mov     ebx, eax
0x18000a038  cmp     [rsp+78h+var_44], 1
0x18000a03d  jz      short loc_18000A04F
0x18000a03f  mov     rdx, [rsp+78h]; unsigned __int64
0x18000a044  mov     r8d, 232h; unsigned __int64
0x18000a04a  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18000a04f  mov     cl, byte ptr [rsp+78h+var_48]; int
0x18000a053  test    cl, cl
0x18000a055  jz      loc_18000A281
0x18000a05b  lea     eax, [rcx-1]
0x18000a05e  cmp     al, 1
0x18000a060  jbe     short loc_18000A076
0x18000a062  mov     rdx, [rsp+78h]; unsigned __int64
0x18000a067  mov     r8d, 235h; unsigned __int64
0x18000a06d  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18000a072  mov     cl, byte ptr [rsp+78h+var_48]
0x18000a076  test    cl, cl
0x18000a078  jz      loc_18000A281
0x18000a07e  test    ebx, ebx
0x18000a080  js      short loc_18000A0A7
0x18000a082  mov     rax, [rdi]
0x18000a085  lea     r9, [rsp+78h+var_44]
0x18000a08a  mov     r8d, 10h
0x18000a090  lea     rdx, [rsp+78h+var_20]
0x18000a095  mov     rcx, rdi
0x18000a098  mov     rax, [rax+18h]
0x18000a09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a1  mov     ebx, eax
0x18000a0a3  mov     cl, byte ptr [rsp+78h+var_48]
0x18000a0a7  cmp     cl, 1
0x18000a0aa  jnz     loc_18000A15D
0x18000a0b0  test    ebx, ebx
0x18000a0b2  js      loc_18000A281
0x18000a0b8  mov     rax, [rdi]
0x18000a0bb  lea     r9, [rsp+78h+var_44]
0x18000a0c0  mov     r8d, 4
0x18000a0c6  lea     rdx, [rsp+78h+var_40]
0x18000a0cb  mov     rcx, rdi
0x18000a0ce  mov     rax, [rax+18h]
0x18000a0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d7  mov     ebx, eax
0x18000a0d9  cmp     [rsp+78h+var_44], 4
0x18000a0de  jz      short loc_18000A0F0
0x18000a0e0  mov     rdx, [rsp+78h]; unsigned __int64
0x18000a0e5  mov     r8d, 249h; unsigned __int64
0x18000a0eb  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18000a0f0  test    ebx, ebx
0x18000a0f2  js      loc_18000A281
0x18000a0f8  lea     rcx, [rsi-8]; this
0x18000a0fc  lea     r9, [rsp+78h+var_38]; unsigned __int8 **
0x18000a101  mov     r8d, [rsp+78h+var_40]; unsigned int
0x18000a106  lea     rdx, [rsp+78h+var_20]; struct _GUID *
0x18000a10b  call    ?AllocateBufferForValue@CMtfPropertyBag@mtf@ipx@@IEAAJAEBU_GUID@@KPEAPEAE@Z; ipx::mtf::CMtfPropertyBag::AllocateBufferForValue(_GUID const &,ulong,uchar * *)
0x18000a110  mov     ebx, eax
0x18000a112  test    eax, eax
0x18000a114  js      loc_180009FE4
0x18000a11a  mov     rax, [rdi]
0x18000a11d  lea     r9, [rsp+78h+var_44]
0x18000a122  mov     r8d, [rsp+78h+var_40]
0x18000a127  mov     rdx, [rsp+78h+var_38]
0x18000a12c  mov     rcx, rdi
0x18000a12f  mov     rax, [rax+18h]
0x18000a133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a138  mov     ebx, eax
0x18000a13a  mov     eax, [rsp+78h+var_40]
0x18000a13e  cmp     [rsp+78h+var_44], eax
0x18000a142  jz      loc_180009FE4
0x18000a148  mov     rdx, [rsp+78h]; unsigned __int64
0x18000a14d  mov     r8d, 256h; unsigned __int64
0x18000a153  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18000a158  jmp     loc_180009FE4
0x18000a15d  xorps   xmm0, xmm0
0x18000a160  movups  [rsp+78h+var_30], xmm0
0x18000a165  test    ebx, ebx
0x18000a167  js      loc_18000A281
0x18000a16d  mov     rax, [rdi]
0x18000a170  lea     r9, [rsp+78h+var_44]
0x18000a175  mov     r8d, 10h
0x18000a17b  lea     rdx, [rsp+78h+var_30]
0x18000a180  mov     rcx, rdi
0x18000a183  mov     rax, [rax+18h]
0x18000a187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18c  mov     ebx, eax
0x18000a18e  cmp     [rsp+78h+var_44], 10h
0x18000a193  jz      short loc_18000A1A5
0x18000a195  mov     rdx, [rsp+78h]; unsigned __int64
0x18000a19a  mov     r8d, 260h; unsigned __int64
0x18000a1a0  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x18000a1a5  test    ebx, ebx
0x18000a1a7  js      loc_18000A281
0x18000a1ad  lea     rax, qword_18003E5D0
0x18000a1b4  mov     rcx, qword ptr [rsp+78h+var_30+8]
0x18000a1b9  mov     rdx, qword ptr [rsp+78h+var_30]
0x18000a1be  cmp     [rax], rdx
0x18000a1c1  jnz     loc_18000A263
0x18000a1c7  cmp     [rax+8], rcx
0x18000a1cb  jnz     loc_18000A263
0x18000a1d1  mov     [rsp+78h+var_38], 0
0x18000a1da  lea     rax, [rsp+78h+var_38]
0x18000a1df  mov     [rsp+78h+var_58], rax
0x18000a1e4  lea     r9, _GUID_06445657_3a07_492d_94c3_052034ef2d12
0x18000a1eb  xor     edx, edx
0x18000a1ed  lea     r8d, [rdx+1]
0x18000a1f1  lea     rcx, [rsp+78h+var_30]
0x18000a1f6  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18000a1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a202  mov     ebx, eax
0x18000a204  test    eax, eax
0x18000a206  js      short loc_18000A23E
0x18000a208  mov     rcx, [rsp+78h+var_38]
0x18000a20d  mov     rax, [rcx]
0x18000a210  mov     rdx, rdi
0x18000a213  mov     rax, [rax+28h]
0x18000a217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a21c  mov     ebx, eax
0x18000a21e  test    eax, eax
0x18000a220  js      short loc_18000A23E
0x18000a222  lea     rcx, [rsi-8]
0x18000a226  mov     rax, [rcx]
0x18000a229  mov     r8, [rsp+78h+var_38]
0x18000a22e  lea     rdx, [rsp+78h+var_20]
0x18000a233  mov     rax, [rax+30h]
0x18000a237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23c  mov     ebx, eax
0x18000a23e  mov     rcx, [rsp+78h+var_38]
0x18000a243  mov     [rsp+78h+var_38], 0
0x18000a24c  test    rcx, rcx
0x18000a24f  jz      short loc_18000A25E
0x18000a251  mov     rax, [rcx]
0x18000a254  mov     rax, [rax+10h]
0x18000a258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25d  nop
0x18000a25e  jmp     loc_180009FE4
0x18000a263  add     rax, 10h
0x18000a267  lea     r8, qword_18003F210
0x18000a26e  cmp     rax, r8
0x18000a271  jnz     loc_18000A1BE
0x18000a277  mov     ebx, 80070057h
0x18000a27c  jmp     loc_180009FE4
0x18000a281  mov     eax, ebx
0x18000a283  jmp     short loc_18000A289
0x18000a285  mov     eax, [rsp+78h+var_40]
0x18000a289  mov     rcx, [rsp+78h+var_10]
0x18000a28e  xor     rcx, rsp; StackCookie
0x18000a291  call    __security_check_cookie
0x18000a296  lea     r11, [rsp+78h+var_8]
0x18000a29b  mov     rbx, [r11+20h]
0x18000a29f  mov     rsi, [r11+28h]
0x18000a2a3  mov     rsp, r11
0x18000a2a6  pop     rdi
0x18000a2a7  retn
```
