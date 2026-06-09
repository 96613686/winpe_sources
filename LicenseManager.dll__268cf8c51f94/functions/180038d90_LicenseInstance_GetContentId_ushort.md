# LicenseInstance::GetContentId(ushort * *)

- ea: `0x180038d90`
- end: `0x180038f86`
- name: `?GetContentId@LicenseInstance@@UEAAJPEAPEAG@Z`
- size: `502`
- prototype: `__int64 __fastcall(LicenseInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180038d90`
- `0x180054a54`
- `0x180064240`
- `0x180075e60`
- `0x1800769f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038deb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038deb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall LicenseInstance::GetContentId(LicenseInstance *this, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rdx
  const WCHAR *v5; // r14
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rdx
  unsigned int v9; // esi
  unsigned __int64 v10; // r8
  unsigned __int16 *v11; // rax
  __int64 v12; // rcx
  WCHAR v13; // r9
  __int64 v14; // r9
  unsigned __int16 *v15; // rcx
  __int64 v16; // rbx
  bool v17; // cf
  __int128 v19; // [rsp+30h] [rbp-48h] BYREF
  __m128i si128; // [rsp+40h] [rbp-38h]

  v3 = *((_QWORD *)this + 3);
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  v4 = (_QWORD *)(v3 + 72);
  if ( &v19 != (__int128 *)(v3 + 72) )
  {
    if ( *(_QWORD *)(v3 + 96) > 7u )
      v4 = (_QWORD *)*v4;
    std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Assign<unsigned short>(
      &v19,
      v4,
      *(_QWORD *)(v3 + 88));
  }
  if ( v3 != -16 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  v5 = (const WCHAR *)&v19;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = (const WCHAR *)v19;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  *a2 = 0;
  v7 = v6 + 1;
  if ( v6 + 1 >= v6 && is_mul_ok(v7, 2u) )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
    *a2 = v8;
    v9 = v8 == 0 ? 0x8007000E : 0;
    if ( !v8 )
      goto LABEL_34;
    if ( v7 > 0x7FFFFFFF )
    {
LABEL_17:
      *v8 = 0;
      goto LABEL_34;
    }
    if ( v6 >= 0x7FFFFFFF )
    {
      if ( v6 == -1 )
        goto LABEL_34;
      goto LABEL_17;
    }
    if ( !v5 )
    {
      v5 = &LocaleName;
      v6 = 0;
    }
    if ( v7 )
    {
      v10 = v7;
      v11 = v8;
      v12 = 0;
      do
      {
        if ( !v6 )
          break;
        v13 = *v5;
        if ( !*v5 )
          break;
        ++v5;
        *v11++ = v13;
        --v6;
        ++v12;
        --v10;
      }
      while ( v10 );
      v14 = v12 - 1;
      if ( v10 )
        v14 = v12;
      v15 = v11 - 1;
      if ( v10 )
        v15 = v11;
      *v15 = 0;
      if ( v10 )
      {
        v17 = v7 == v14;
        v16 = v7 - v14;
        if ( !v17 && v16 != 1 && (unsigned __int64)(2 * v16) > 2 )
          memset_0(&v8[v14 + 1], 0, 2 * v16 - 2);
      }
    }
  }
  else
  {
    v9 = -2147024362;
  }
LABEL_34:
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v19, 2 * si128.m128i_i64[1] + 2);
  return v9;
}

```

## disassembly

```asm
0x180038d90  mov     r11, rsp
0x180038d93  mov     [r11+18h], rbx
0x180038d97  mov     [r11+20h], rsi
0x180038d9b  push    rdi
0x180038d9c  push    r14
0x180038d9e  push    r15
0x180038da0  sub     rsp, 60h
0x180038da4  mov     rax, cs:__security_cookie
0x180038dab  xor     rax, rsp
0x180038dae  mov     [rsp+78h+var_28], rax
0x180038db3  mov     rsi, rdx
0x180038db6  xor     r15d, r15d
0x180038db9  mov     [r11-58h], r15d
0x180038dbd  mov     rbx, [rcx+18h]
0x180038dc1  xorps   xmm0, xmm0
0x180038dc4  movups  [rsp+78h+var_48], xmm0
0x180038dc9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180038dd1  movdqu  [rsp+78h+var_38], xmm1
0x180038dd7  mov     [r11-48h], r15w
0x180038ddc  mov     [rsp+78h+var_58], 1
0x180038de4  lea     rdi, [rbx+10h]
0x180038de8  mov     rcx, rdi; lpCriticalSection
0x180038deb  call    cs:__imp_EnterCriticalSection
0x180038df1  mov     [rsp+78h+var_50], rdi
0x180038df6  lea     rdx, [rbx+48h]
0x180038dfa  lea     rax, [rsp+78h+var_48]
0x180038dff  cmp     rax, rdx
0x180038e02  jz      short loc_180038E1D
0x180038e04  mov     r8, [rdx+10h]
0x180038e08  cmp     qword ptr [rdx+18h], 7
0x180038e0d  jbe     short loc_180038E12
0x180038e0f  mov     rdx, [rdx]
0x180038e12  lea     rcx, [rsp+78h+var_48]
0x180038e17  call    ??$_Assign@G@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@AEAAAEAV01@QEBG_K@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180038e1c  nop
0x180038e1d  test    rdi, rdi
0x180038e20  jz      short loc_180038E2B
0x180038e22  mov     rcx, rdi; lpCriticalSection
0x180038e25  call    cs:__imp_LeaveCriticalSection
0x180038e2b  lea     r14, [rsp+78h+var_48]
0x180038e30  cmp     qword ptr [rsp+78h+var_38+8], 7
0x180038e36  cmova   r14, qword ptr [rsp+78h+var_48]
0x180038e3c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038e40  inc     rdi
0x180038e43  cmp     [r14+rdi*2], r15w
0x180038e48  jnz     short loc_180038E40
0x180038e4a  mov     [rsi], r15
0x180038e4d  lea     rbx, [rdi+1]
0x180038e51  cmp     rbx, rdi
0x180038e54  jb      loc_180038F38
0x180038e5a  mov     eax, 2
0x180038e5f  mul     rbx
0x180038e62  test    rdx, rdx
0x180038e65  jnz     loc_180038F38
0x180038e6b  mov     rcx, rax; cb
0x180038e6e  call    cs:__imp_CoTaskMemAlloc
0x180038e74  mov     rdx, rax
0x180038e77  mov     [rsi], rax
0x180038e7a  mov     rcx, rax
0x180038e7d  neg     rcx
0x180038e80  sbb     esi, esi
0x180038e82  not     esi
0x180038e84  and     esi, 8007000Eh
0x180038e8a  test    rax, rax
0x180038e8d  jz      loc_180038F3D
0x180038e93  mov     eax, 7FFFFFFFh
0x180038e98  cmp     rbx, rax
0x180038e9b  ja      short loc_180038EAB
0x180038e9d  cmp     rdi, rax
0x180038ea0  jb      short loc_180038EB4
0x180038ea2  test    rbx, rbx
0x180038ea5  jz      loc_180038F3D
0x180038eab  mov     [rdx], r15w
0x180038eaf  jmp     loc_180038F3D
0x180038eb4  test    r14, r14
0x180038eb7  jnz     short loc_180038EC3
0x180038eb9  lea     r14, LocaleName
0x180038ec0  mov     rdi, r15
0x180038ec3  test    rbx, rbx
0x180038ec6  jz      short loc_180038F3D
0x180038ec8  mov     r8, rbx
0x180038ecb  mov     rax, rdx
0x180038ece  mov     rcx, r15
0x180038ed1  test    rdi, rdi
0x180038ed4  jz      short loc_180038EF8
0x180038ed6  movzx   r9d, word ptr [r14]
0x180038eda  test    r9w, r9w
0x180038ede  jz      short loc_180038EF8
0x180038ee0  add     r14, 2
0x180038ee4  mov     [rax], r9w
0x180038ee8  add     rax, 2
0x180038eec  dec     rdi
0x180038eef  inc     rcx
0x180038ef2  sub     r8, 1
0x180038ef6  jnz     short loc_180038ED1
0x180038ef8  lea     r9, [rcx-1]
0x180038efc  test    r8, r8
0x180038eff  cmovnz  r9, rcx
0x180038f03  lea     rcx, [rax-2]
0x180038f07  cmovnz  rcx, rax
0x180038f0b  mov     [rcx], r15w
0x180038f0f  jz      short loc_180038F3D
0x180038f11  sub     rbx, r9
0x180038f14  cmp     rbx, 1
0x180038f18  jbe     short loc_180038F3D
0x180038f1a  lea     r8, [rbx+rbx]
0x180038f1e  cmp     r8, 2
0x180038f22  jbe     short loc_180038F3D
0x180038f24  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180038f28  inc     r9
0x180038f2b  lea     rcx, [rdx+r9*2]; void *
0x180038f2f  xor     edx, edx; Val
0x180038f31  call    memset_0
0x180038f36  jmp     short loc_180038F3D
0x180038f38  mov     esi, 80070216h
0x180038f3d  mov     rdx, qword ptr [rsp+78h+var_38+8]
0x180038f42  cmp     rdx, 7
0x180038f46  jbe     short loc_180038F5A
0x180038f48  lea     rdx, ds:2[rdx*2]
0x180038f50  mov     rcx, qword ptr [rsp+78h+var_48]
0x180038f55  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180038f5a  mov     eax, esi
0x180038f5c  jmp     short loc_180038F62
0x180038f5e  mov     eax, [rsp+78h+var_58]
0x180038f62  mov     rcx, [rsp+78h+var_28]
0x180038f67  xor     rcx, rsp; StackCookie
0x180038f6a  call    __security_check_cookie
0x180038f6f  lea     r11, [rsp+78h+var_18]
0x180038f74  mov     rbx, [r11+30h]
0x180038f78  mov     rsi, [r11+38h]
0x180038f7c  mov     rsp, r11
0x180038f7f  pop     r15
0x180038f81  pop     r14
0x180038f83  pop     rdi
0x180038f84  retn
```
