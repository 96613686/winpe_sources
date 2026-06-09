# TpmKey20::~TpmKey20(void)

- ea: `0x180040b20`
- end: `0x180041097`
- name: `??1TpmKey20@@UEAA@XZ`
- size: `1399`
- prototype: `void __fastcall(TpmKey20 *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800409f8`
- `0x180040aac`
- `0x1800410a0`
- `0x180087ef0`
- `0x1800c4b4a`

## callees

- `0x18000e970`
- `0x18003f71c`
- `0x180040b20`
- `0x1800500a8`
- `0x1800768a0`
- `0x18007c808`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041075`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041075`

## pseudocode

```c
void __fastcall TpmKey20::~TpmKey20(TpmKey20 *this)
{
  const struct std::nothrow_t *v2; // rdx
  _BYTE *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rcx
  _BYTE *v7; // rax
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int64 v10; // rcx
  _BYTE *v11; // rax
  __int64 v12; // rcx
  _BYTE *v13; // rax
  __int64 v14; // rcx
  _BYTE *v15; // rax
  __int64 v16; // rcx
  _BYTE *v17; // rax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  __int64 v20; // rcx
  _BYTE *v21; // rax
  __int64 v22; // rcx
  _BYTE *v23; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  __int64 v26; // rcx
  _BYTE *v27; // rax
  __int64 v28; // rcx
  _BYTE *v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  __int64 v32; // rcx
  _BYTE *v33; // rax
  __int64 v34; // rcx
  _BYTE *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  const struct std::nothrow_t *v39; // rdx
  _BYTE *v40; // rax
  __int64 v41; // rcx

  *(_QWORD *)this = &TpmKey20::`vftable';
  TpmKey20::UnLoadKeyFromTpm(this);
  v3 = (_BYTE *)*((_QWORD *)this + 81);
  if ( v3 )
  {
    v4 = *((unsigned int *)this + 164);
    if ( *((_DWORD *)this + 164) )
    {
      do
      {
        *v3++ = 0;
        --v4;
      }
      while ( v4 );
    }
    operator delete(*((void **)this + 81), v2);
    *((_QWORD *)this + 81) = 0;
  }
  v5 = (_BYTE *)*((_QWORD *)this + 83);
  if ( v5 )
  {
    v6 = *((unsigned int *)this + 168);
    if ( *((_DWORD *)this + 168) )
    {
      do
      {
        *v5++ = 0;
        --v6;
      }
      while ( v6 );
    }
    operator delete(*((void **)this + 83), v2);
    *((_QWORD *)this + 83) = 0;
  }
  v7 = (_BYTE *)*((_QWORD *)this + 114);
  if ( v7 )
  {
    v8 = *((unsigned int *)this + 227);
    if ( *((_DWORD *)this + 227) )
    {
      do
      {
        *v7++ = 0;
        --v8;
      }
      while ( v8 );
    }
    operator delete(*((void **)this + 114), v2);
    *((_QWORD *)this + 114) = 0;
  }
  v9 = (_BYTE *)*((_QWORD *)this + 116);
  if ( v9 )
  {
    v10 = *((unsigned int *)this + 230);
    if ( *((_DWORD *)this + 230) )
    {
      do
      {
        *v9++ = 0;
        --v10;
      }
      while ( v10 );
    }
    operator delete(*((void **)this + 116), v2);
    *((_QWORD *)this + 116) = 0;
  }
  v11 = (_BYTE *)*((_QWORD *)this + 118);
  if ( v11 )
  {
    v12 = *((unsigned int *)this + 234);
    if ( *((_DWORD *)this + 234) )
    {
      do
      {
        *v11++ = 0;
        --v12;
      }
      while ( v12 );
    }
    operator delete(*((void **)this + 118), v2);
    *((_QWORD *)this + 118) = 0;
  }
  v13 = (_BYTE *)*((_QWORD *)this + 86);
  if ( v13 )
  {
    v14 = *((unsigned int *)this + 171);
    if ( *((_DWORD *)this + 171) )
    {
      do
      {
        *v13++ = 0;
        --v14;
      }
      while ( v14 );
    }
    operator delete(*((void **)this + 86), v2);
    *((_QWORD *)this + 86) = 0;
  }
  v15 = (_BYTE *)*((_QWORD *)this + 88);
  if ( v15 )
  {
    v16 = *((unsigned int *)this + 178);
    if ( *((_DWORD *)this + 178) )
    {
      do
      {
        *v15++ = 0;
        --v16;
      }
      while ( v16 );
    }
    operator delete(*((void **)this + 88), v2);
    *((_QWORD *)this + 88) = 0;
  }
  v17 = (_BYTE *)*((_QWORD *)this + 90);
  if ( v17 )
  {
    v18 = *((unsigned int *)this + 182);
    if ( *((_DWORD *)this + 182) )
    {
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
    }
    operator delete(*((void **)this + 90), v2);
    *((_QWORD *)this + 90) = 0;
  }
  v19 = (_BYTE *)*((_QWORD *)this + 92);
  if ( v19 )
  {
    v20 = *((unsigned int *)this + 186);
    if ( *((_DWORD *)this + 186) )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    operator delete(*((void **)this + 92), v2);
    *((_QWORD *)this + 92) = 0;
  }
  v21 = (_BYTE *)*((_QWORD *)this + 94);
  if ( v21 )
  {
    v22 = *((unsigned int *)this + 190);
    if ( *((_DWORD *)this + 190) )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
    }
    operator delete(*((void **)this + 94), v2);
    *((_QWORD *)this + 94) = 0;
  }
  v23 = (_BYTE *)*((_QWORD *)this + 96);
  if ( v23 )
  {
    v24 = *((unsigned int *)this + 194);
    if ( *((_DWORD *)this + 194) )
    {
      do
      {
        *v23++ = 0;
        --v24;
      }
      while ( v24 );
    }
    operator delete(*((void **)this + 96), v2);
    *((_QWORD *)this + 96) = 0;
  }
  v25 = (_BYTE *)*((_QWORD *)this + 98);
  if ( v25 )
  {
    v26 = *((unsigned int *)this + 198);
    if ( *((_DWORD *)this + 198) )
    {
      do
      {
        *v25++ = 0;
        --v26;
      }
      while ( v26 );
    }
    operator delete(*((void **)this + 98), v2);
    *((_QWORD *)this + 98) = 0;
  }
  v27 = (_BYTE *)*((_QWORD *)this + 100);
  if ( v27 )
  {
    v28 = *((unsigned int *)this + 202);
    if ( *((_DWORD *)this + 202) )
    {
      do
      {
        *v27++ = 0;
        --v28;
      }
      while ( v28 );
    }
    operator delete(*((void **)this + 100), v2);
    *((_QWORD *)this + 100) = 0;
  }
  v29 = (_BYTE *)*((_QWORD *)this + 102);
  if ( v29 )
  {
    v30 = *((unsigned int *)this + 206);
    if ( *((_DWORD *)this + 206) )
    {
      do
      {
        *v29++ = 0;
        --v30;
      }
      while ( v30 );
    }
    operator delete(*((void **)this + 102), v2);
    *((_QWORD *)this + 102) = 0;
  }
  v31 = (_BYTE *)*((_QWORD *)this + 119);
  if ( v31 )
  {
    v32 = *((unsigned int *)this + 240);
    if ( *((_DWORD *)this + 240) )
    {
      do
      {
        *v31++ = 0;
        --v32;
      }
      while ( v32 );
    }
    operator delete(*((void **)this + 119), v2);
    *((_QWORD *)this + 119) = 0;
  }
  v33 = (_BYTE *)*((_QWORD *)this + 121);
  if ( v33 )
  {
    v34 = *((unsigned int *)this + 244);
    if ( *((_DWORD *)this + 244) )
    {
      do
      {
        *v33++ = 0;
        --v34;
      }
      while ( v34 );
    }
    operator delete(*((void **)this + 121), v2);
    *((_QWORD *)this + 121) = 0;
  }
  v35 = (_BYTE *)*((_QWORD *)this + 123);
  if ( v35 )
  {
    v36 = *((unsigned int *)this + 248);
    if ( *((_DWORD *)this + 248) )
    {
      do
      {
        *v35++ = 0;
        --v36;
      }
      while ( v36 );
    }
    operator delete(*((void **)this + 123), v2);
    *((_QWORD *)this + 123) = 0;
  }
  v37 = *((_QWORD *)this + 11);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 32LL))(v37, 1);
    *((_QWORD *)this + 11) = 0;
  }
  v38 = *((_QWORD *)this + 12);
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 32LL))(v38, 1);
    *((_QWORD *)this + 12) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcpKspSddidk>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PcpKspSddidk>::GetImpl'::`2'::impl) )
  {
    v40 = (_BYTE *)*((_QWORD *)this + 126);
    if ( v40 )
    {
      v41 = *((unsigned int *)this + 254);
      if ( *((_DWORD *)this + 254) )
      {
        do
        {
          *v40++ = 0;
          --v41;
        }
        while ( v41 );
      }
      operator delete(*((void **)this + 126), v39);
      *((_QWORD *)this + 126) = 0;
    }
  }
  tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST((TpmKey20 *)((char *)this + 832));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 568));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 488));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 392));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 320));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 248));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 176));
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((TpmKey20 *)((char *)this + 104));
  *(_QWORD *)this = &TpmObject::`vftable';
  if ( (*((_DWORD *)this + 3) & 1) == 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &ObjectWithProperties::`vftable';
}

```

## disassembly

```asm
0x180040b20  mov     [rsp+arg_0], rbx
0x180040b25  push    rdi
0x180040b26  sub     rsp, 20h
0x180040b2a  mov     rbx, rcx
0x180040b2d  lea     rax, ??_7TpmKey20@@6B@; const TpmKey20::`vftable'
0x180040b34  mov     [rcx], rax
0x180040b37  call    ?UnLoadKeyFromTpm@TpmKey20@@IEAAJXZ; TpmKey20::UnLoadKeyFromTpm(void)
0x180040b3c  mov     rax, [rbx+288h]
0x180040b43  xor     edi, edi
0x180040b45  test    rax, rax
0x180040b48  jz      short loc_180040B80
0x180040b4a  mov     ecx, [rbx+290h]
0x180040b50  test    rcx, rcx
0x180040b53  jz      short loc_180040B6D
0x180040b55  nop     word ptr [rax+rax+00000000h]
0x180040b60  mov     [rax], dil
0x180040b63  lea     rax, [rax+1]
0x180040b67  sub     rcx, 1
0x180040b6b  jnz     short loc_180040B60
0x180040b6d  mov     rcx, [rbx+288h]; void *
0x180040b74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040b79  mov     [rbx+288h], rdi
0x180040b80  mov     rax, [rbx+298h]
0x180040b87  test    rax, rax
0x180040b8a  jz      short loc_180040BC0
0x180040b8c  mov     ecx, [rbx+2A0h]
0x180040b92  test    rcx, rcx
0x180040b95  jz      short loc_180040BAD
0x180040b97  nop     word ptr [rax+rax+00000000h]
0x180040ba0  mov     [rax], dil
0x180040ba3  lea     rax, [rax+1]
0x180040ba7  sub     rcx, 1
0x180040bab  jnz     short loc_180040BA0
0x180040bad  mov     rcx, [rbx+298h]; void *
0x180040bb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040bb9  mov     [rbx+298h], rdi
0x180040bc0  mov     rax, [rbx+390h]
0x180040bc7  test    rax, rax
0x180040bca  jz      short loc_180040C00
0x180040bcc  mov     ecx, [rbx+38Ch]
0x180040bd2  test    rcx, rcx
0x180040bd5  jz      short loc_180040BED
0x180040bd7  nop     word ptr [rax+rax+00000000h]
0x180040be0  mov     [rax], dil
0x180040be3  lea     rax, [rax+1]
0x180040be7  sub     rcx, 1
0x180040beb  jnz     short loc_180040BE0
0x180040bed  mov     rcx, [rbx+390h]; void *
0x180040bf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040bf9  mov     [rbx+390h], rdi
0x180040c00  mov     rax, [rbx+3A0h]
0x180040c07  test    rax, rax
0x180040c0a  jz      short loc_180040C40
0x180040c0c  mov     ecx, [rbx+398h]
0x180040c12  test    rcx, rcx
0x180040c15  jz      short loc_180040C2D
0x180040c17  nop     word ptr [rax+rax+00000000h]
0x180040c20  mov     [rax], dil
0x180040c23  lea     rax, [rax+1]
0x180040c27  sub     rcx, 1
0x180040c2b  jnz     short loc_180040C20
0x180040c2d  mov     rcx, [rbx+3A0h]; void *
0x180040c34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040c39  mov     [rbx+3A0h], rdi
0x180040c40  mov     rax, [rbx+3B0h]
0x180040c47  test    rax, rax
0x180040c4a  jz      short loc_180040C80
0x180040c4c  mov     ecx, [rbx+3A8h]
0x180040c52  test    rcx, rcx
0x180040c55  jz      short loc_180040C6D
0x180040c57  nop     word ptr [rax+rax+00000000h]
0x180040c60  mov     [rax], dil
0x180040c63  lea     rax, [rax+1]
0x180040c67  sub     rcx, 1
0x180040c6b  jnz     short loc_180040C60
0x180040c6d  mov     rcx, [rbx+3B0h]; void *
0x180040c74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040c79  mov     [rbx+3B0h], rdi
0x180040c80  mov     rax, [rbx+2B0h]
0x180040c87  test    rax, rax
0x180040c8a  jz      short loc_180040CC0
0x180040c8c  mov     ecx, [rbx+2ACh]
0x180040c92  test    rcx, rcx
0x180040c95  jz      short loc_180040CAD
0x180040c97  nop     word ptr [rax+rax+00000000h]
0x180040ca0  mov     [rax], dil
0x180040ca3  lea     rax, [rax+1]
0x180040ca7  sub     rcx, 1
0x180040cab  jnz     short loc_180040CA0
0x180040cad  mov     rcx, [rbx+2B0h]; void *
0x180040cb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040cb9  mov     [rbx+2B0h], rdi
0x180040cc0  mov     rax, [rbx+2C0h]
0x180040cc7  test    rax, rax
0x180040cca  jz      short loc_180040D00
0x180040ccc  mov     ecx, [rbx+2C8h]
0x180040cd2  test    rcx, rcx
0x180040cd5  jz      short loc_180040CED
0x180040cd7  nop     word ptr [rax+rax+00000000h]
0x180040ce0  mov     [rax], dil
0x180040ce3  lea     rax, [rax+1]
0x180040ce7  sub     rcx, 1
0x180040ceb  jnz     short loc_180040CE0
0x180040ced  mov     rcx, [rbx+2C0h]; void *
0x180040cf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040cf9  mov     [rbx+2C0h], rdi
0x180040d00  mov     rax, [rbx+2D0h]
0x180040d07  test    rax, rax
0x180040d0a  jz      short loc_180040D40
0x180040d0c  mov     ecx, [rbx+2D8h]
0x180040d12  test    rcx, rcx
0x180040d15  jz      short loc_180040D2D
0x180040d17  nop     word ptr [rax+rax+00000000h]
0x180040d20  mov     [rax], dil
0x180040d23  lea     rax, [rax+1]
0x180040d27  sub     rcx, 1
0x180040d2b  jnz     short loc_180040D20
0x180040d2d  mov     rcx, [rbx+2D0h]; void *
0x180040d34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040d39  mov     [rbx+2D0h], rdi
0x180040d40  mov     rax, [rbx+2E0h]
0x180040d47  test    rax, rax
0x180040d4a  jz      short loc_180040D80
0x180040d4c  mov     ecx, [rbx+2E8h]
0x180040d52  test    rcx, rcx
0x180040d55  jz      short loc_180040D6D
0x180040d57  nop     word ptr [rax+rax+00000000h]
0x180040d60  mov     [rax], dil
0x180040d63  lea     rax, [rax+1]
0x180040d67  sub     rcx, 1
0x180040d6b  jnz     short loc_180040D60
0x180040d6d  mov     rcx, [rbx+2E0h]; void *
0x180040d74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040d79  mov     [rbx+2E0h], rdi
0x180040d80  mov     rax, [rbx+2F0h]
0x180040d87  test    rax, rax
0x180040d8a  jz      short loc_180040DC0
0x180040d8c  mov     ecx, [rbx+2F8h]
0x180040d92  test    rcx, rcx
0x180040d95  jz      short loc_180040DAD
0x180040d97  nop     word ptr [rax+rax+00000000h]
0x180040da0  mov     [rax], dil
0x180040da3  lea     rax, [rax+1]
0x180040da7  sub     rcx, 1
0x180040dab  jnz     short loc_180040DA0
0x180040dad  mov     rcx, [rbx+2F0h]; void *
0x180040db4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040db9  mov     [rbx+2F0h], rdi
0x180040dc0  mov     rax, [rbx+300h]
0x180040dc7  test    rax, rax
0x180040dca  jz      short loc_180040E00
0x180040dcc  mov     ecx, [rbx+308h]
0x180040dd2  test    rcx, rcx
0x180040dd5  jz      short loc_180040DED
0x180040dd7  nop     word ptr [rax+rax+00000000h]
0x180040de0  mov     [rax], dil
0x180040de3  lea     rax, [rax+1]
0x180040de7  sub     rcx, 1
0x180040deb  jnz     short loc_180040DE0
0x180040ded  mov     rcx, [rbx+300h]; void *
0x180040df4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040df9  mov     [rbx+300h], rdi
0x180040e00  mov     rax, [rbx+310h]
0x180040e07  test    rax, rax
0x180040e0a  jz      short loc_180040E40
0x180040e0c  mov     ecx, [rbx+318h]
0x180040e12  test    rcx, rcx
0x180040e15  jz      short loc_180040E2D
0x180040e17  nop     word ptr [rax+rax+00000000h]
0x180040e20  mov     [rax], dil
0x180040e23  lea     rax, [rax+1]
0x180040e27  sub     rcx, 1
0x180040e2b  jnz     short loc_180040E20
0x180040e2d  mov     rcx, [rbx+310h]; void *
0x180040e34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040e39  mov     [rbx+310h], rdi
0x180040e40  mov     rax, [rbx+320h]
0x180040e47  test    rax, rax
0x180040e4a  jz      short loc_180040E80
0x180040e4c  mov     ecx, [rbx+328h]
0x180040e52  test    rcx, rcx
0x180040e55  jz      short loc_180040E6D
0x180040e57  nop     word ptr [rax+rax+00000000h]
0x180040e60  mov     [rax], dil
0x180040e63  lea     rax, [rax+1]
0x180040e67  sub     rcx, 1
0x180040e6b  jnz     short loc_180040E60
0x180040e6d  mov     rcx, [rbx+320h]; void *
0x180040e74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040e79  mov     [rbx+320h], rdi
0x180040e80  mov     rax, [rbx+330h]
0x180040e87  test    rax, rax
0x180040e8a  jz      short loc_180040EC0
0x180040e8c  mov     ecx, [rbx+338h]
0x180040e92  test    rcx, rcx
0x180040e95  jz      short loc_180040EAD
0x180040e97  nop     word ptr [rax+rax+00000000h]
0x180040ea0  mov     [rax], dil
0x180040ea3  lea     rax, [rax+1]
0x180040ea7  sub     rcx, 1
0x180040eab  jnz     short loc_180040EA0
0x180040ead  mov     rcx, [rbx+330h]; void *
0x180040eb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040eb9  mov     [rbx+330h], rdi
0x180040ec0  mov     rax, [rbx+3B8h]
0x180040ec7  test    rax, rax
0x180040eca  jz      short loc_180040F00
0x180040ecc  mov     ecx, [rbx+3C0h]
0x180040ed2  test    rcx, rcx
0x180040ed5  jz      short loc_180040EED
0x180040ed7  nop     word ptr [rax+rax+00000000h]
0x180040ee0  mov     [rax], dil
0x180040ee3  lea     rax, [rax+1]
0x180040ee7  sub     rcx, 1
0x180040eeb  jnz     short loc_180040EE0
0x180040eed  mov     rcx, [rbx+3B8h]; void *
0x180040ef4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040ef9  mov     [rbx+3B8h], rdi
0x180040f00  mov     rax, [rbx+3C8h]
0x180040f07  test    rax, rax
0x180040f0a  jz      short loc_180040F40
0x180040f0c  mov     ecx, [rbx+3D0h]
0x180040f12  test    rcx, rcx
0x180040f15  jz      short loc_180040F2D
0x180040f17  nop     word ptr [rax+rax+00000000h]
0x180040f20  mov     [rax], dil
0x180040f23  lea     rax, [rax+1]
0x180040f27  sub     rcx, 1
0x180040f2b  jnz     short loc_180040F20
0x180040f2d  mov     rcx, [rbx+3C8h]; void *
0x180040f34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040f39  mov     [rbx+3C8h], rdi
0x180040f40  mov     rax, [rbx+3D8h]
0x180040f47  test    rax, rax
0x180040f4a  jz      short loc_180040F80
0x180040f4c  mov     ecx, [rbx+3E0h]
0x180040f52  test    rcx, rcx
0x180040f55  jz      short loc_180040F6D
0x180040f57  nop     word ptr [rax+rax+00000000h]
0x180040f60  mov     [rax], dil
0x180040f63  lea     rax, [rax+1]
0x180040f67  sub     rcx, 1
0x180040f6b  jnz     short loc_180040F60
0x180040f6d  mov     rcx, [rbx+3D8h]; void *
0x180040f74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040f79  mov     [rbx+3D8h], rdi
0x180040f80  mov     rcx, [rbx+58h]
0x180040f84  test    rcx, rcx
0x180040f87  jz      short loc_180040F9E
0x180040f89  mov     rax, [rcx]
0x180040f8c  mov     edx, 1
0x180040f91  mov     rax, [rax+20h]
0x180040f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f9a  mov     [rbx+58h], rdi
0x180040f9e  mov     rcx, [rbx+60h]
0x180040fa2  test    rcx, rcx
0x180040fa5  jz      short loc_180040FBC
0x180040fa7  mov     rax, [rcx]
0x180040faa  mov     edx, 1
0x180040faf  mov     rax, [rax+20h]
0x180040fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fb8  mov     [rbx+60h], rdi
0x180040fbc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcpKspSddidk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcpKspSddidk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcpKspSddidk> `wil::Feature<__WilFeatureTraits_Feature_PcpKspSddidk>::GetImpl(void)'::`2'::impl
0x180040fc3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcpKspSddidk@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcpKspSddidk>::__private_IsEnabled(void)
0x180040fc8  test    al, al
0x180040fca  jz      short loc_180041003
0x180040fcc  mov     rax, [rbx+3F0h]
0x180040fd3  test    rax, rax
0x180040fd6  jz      short loc_180041003
0x180040fd8  mov     ecx, [rbx+3F8h]
0x180040fde  test    rcx, rcx
0x180040fe1  jz      short loc_180040FF0
0x180040fe3  mov     [rax], dil
0x180040fe6  lea     rax, [rax+1]
0x180040fea  sub     rcx, 1
0x180040fee  jnz     short loc_180040FE3
0x180040ff0  mov     rcx, [rbx+3F0h]; void *
0x180040ff7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040ffc  mov     [rbx+3F0h], rdi
0x180041003  lea     rcx, [rbx+340h]; this
0x18004100a  call    ??1TPMW8L_DIGEST@tpm12class@@UEAA@XZ; tpm12class::TPMW8L_DIGEST::~TPMW8L_DIGEST(void)
0x18004100f  lea     rcx, [rbx+238h]; this
0x180041016  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18004101b  lea     rcx, [rbx+1E8h]; this
0x180041022  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x180041027  lea     rcx, [rbx+188h]; this
0x18004102e  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x180041033  lea     rcx, [rbx+140h]; this
0x18004103a  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18004103f  lea     rcx, [rbx+0F8h]; this
0x180041046  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x18004104b  lea     rcx, [rbx+0B0h]; this
0x180041052  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x180041057  lea     rcx, [rbx+68h]; this
0x18004105b  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x180041060  lea     rax, ??_7TpmObject@@6B@; const TpmObject::`vftable'
0x180041067  mov     [rbx], rax
0x18004106a  mov     eax, [rbx+0Ch]
0x18004106d  test    al, 1
0x18004106f  jnz     short loc_180041081
  ... truncated ...
```
