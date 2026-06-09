# CDsmPropertyCache::_PropVariantToDevProp(tagPROPVARIANT const *,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,_DEVPROPERTY *)

- ea: `0x180006a80`
- end: `0x180007090`
- name: `?_PropVariantToDevProp@CDsmPropertyCache@@AEAAJPEBUtagPROPVARIANT@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEAU_DEVPROPERTY@@@Z`
- size: `1552`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005ed0`
- `0x1800061f0`
- `0x180006770`

## callees

- `0x180006a80`
- `0x18000e8e4`
- `0x180021790`
- `0x180022070`
- `0x180027678`
- `0x1800276d0`
- `0x180027ba8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006fa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb6`

## pseudocode

```c
__int64 __fastcall CDsmPropertyCache::_PropVariantToDevProp(__int64 a1, unsigned __int16 *a2, char a3, __int64 a4)
{
  unsigned int v7; // ecx
  const wchar_t *v8; // rbx
  __int64 v9; // r13
  __int64 v10; // rax
  bool v11; // zf
  SIZE_T v12; // rdi
  const wchar_t *v13; // rcx
  size_t v14; // r8
  _WORD *v15; // r11
  unsigned int v16; // r15d
  _BYTE *v18; // rax
  int v19; // ecx
  _DWORD *v20; // rax
  size_t v21; // rdi
  HRESULT v22; // eax
  size_t v23; // rdx
  size_t *v24; // r8
  unsigned int v25; // ecx
  unsigned int v26; // r8d
  int v27; // ebp
  __int64 v28; // r9
  unsigned int i; // edx
  __int64 v30; // rax
  unsigned __int16 *v31; // rsi
  LPVOID v32; // rax
  void *v33; // r12
  unsigned __int16 *v34; // rdx
  __int64 v35; // r8
  __int64 *v36; // r14
  PVOID *v37; // r10
  int v38; // ebx
  unsigned int v39; // edi
  _WORD *v40; // rsi
  __int64 v41; // r8
  __int64 v42; // rcx
  _WORD *v43; // r9
  _WORD *v44; // rdx
  __int64 v45; // rcx
  const wchar_t *v46; // r9
  _OWORD *v47; // rax
  int v48; // edi
  void *v49; // rax
  size_t v50; // [rsp+20h] [rbp-48h]
  unsigned int v51; // [rsp+70h] [rbp+8h]

  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_OWORD *)(a4 + 32) = 0;
  v7 = *a2;
  if ( v7 == 31 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids,
        *((_QWORD *)a2 + 1));
    v8 = (const wchar_t *)*((_QWORD *)a2 + 1);
    v9 = -1;
    if ( !v8 )
    {
      v15 = 0;
      v16 = 0;
      do
LABEL_20:
        v11 = v15[++v9] == 0;
      while ( !v11 );
      *(_QWORD *)(a4 + 40) = v15;
      *(_DWORD *)(a4 + 36) = 2 * v9 + 2;
      v19 = 25;
      if ( (a3 & 1) == 0 )
        v19 = 18;
      *(_DWORD *)(a4 + 32) = v19;
      return v16;
    }
    v10 = -1;
    do
      v11 = v8[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
    v15 = CoTaskMemAlloc(v12);
    if ( !v15 )
    {
      v16 = -2147024882;
      goto LABEL_8;
    }
    v21 = v12 >> 1;
    v22 = StringValidateDestW(v13, v21, v14);
    v16 = v22;
    if ( v22 < 0 )
    {
      if ( v21 )
      {
        *v15 = 0;
LABEL_33:
        CoTaskMemFree(v15);
        v15 = 0;
LABEL_8:
        if ( (v16 & 0x80000000) != 0 )
        {
          if ( v15 )
            CoTaskMemFree(v15);
          return v16;
        }
        goto LABEL_20;
      }
    }
    else
    {
      v22 = StringCopyWorkerW_0(v15, v23, v24, v8, v50);
    }
    v16 = v22;
    if ( !v22 )
      goto LABEL_8;
    goto LABEL_33;
  }
  if ( v7 > 0x48 )
  {
    v25 = v7 - 4113;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids,
          **((unsigned __int8 **)a2 + 2));
      v48 = *((_DWORD *)a2 + 2);
      v49 = CoTaskMemAlloc(v48);
      *(_QWORD *)(a4 + 40) = v49;
      if ( v49 )
      {
        v16 = 0;
        memcpy_s(v49, v48, *((const void *const *)a2 + 2), v48);
        *(_DWORD *)(a4 + 32) = 4099;
        *(_DWORD *)(a4 + 36) = v48;
        return v16;
      }
      return (unsigned int)-2147024882;
    }
    if ( v25 != 14 )
      return (unsigned int)-2147467259;
    v26 = *((_DWORD *)a2 + 2);
    v27 = 1;
    v16 = -2147467259;
    v51 = 1;
    if ( v26 )
    {
      v28 = *((_QWORD *)a2 + 2);
      for ( i = 0; i < v26; ++i )
      {
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)(*(_QWORD *)(v28 + 8LL * i) + 2 * v30) );
        v27 += v30 + 1;
      }
      v51 = v27;
    }
    v31 = a2;
    v32 = CoTaskMemAlloc(2LL * v27);
    v33 = v32;
    if ( v32 )
    {
      v34 = a2;
      *((_WORD *)v32 + v27 - 1) = 0;
      if ( *((_DWORD *)a2 + 2) )
      {
        v35 = *((_QWORD *)v31 + 2);
        v36 = (__int64 *)(v31 + 8);
        v37 = (PVOID *)WPP_GLOBAL_Control;
        v38 = v27;
        v39 = 0;
        v40 = v32;
        do
        {
          if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
          {
            WPP_SF_S(v37[2], 22, &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids, *(_QWORD *)(v35 + 8LL * v39));
            v37 = (PVOID *)WPP_GLOBAL_Control;
            v34 = a2;
          }
          v41 = v38;
          if ( v38 )
          {
            if ( (unsigned __int64)v38 > 0x7FFFFFFF )
            {
              v16 = -2147024809;
              *v40 = 0;
              goto LABEL_66;
            }
            v42 = 2147483646;
            v43 = v40;
            v16 = 0;
            v44 = *(_WORD **)(*((_QWORD *)v34 + 2) + 8LL * v39);
            while ( v42 )
            {
              if ( !*v44 )
              {
                if ( !v41 )
                {
LABEL_56:
                  --v43;
                  v16 = -2147024774;
                  break;
                }
                break;
              }
              *v43++ = *v44++;
              --v42;
              if ( !--v41 )
                goto LABEL_56;
            }
            v34 = a2;
            *v43 = 0;
            v37 = (PVOID *)WPP_GLOBAL_Control;
          }
          else
          {
            v16 = -2147024809;
          }
          if ( (v16 & 0x80000000) != 0 )
            goto LABEL_66;
          v35 = *v36;
          v45 = -1;
          do
            ++v45;
          while ( *(_WORD *)(*(_QWORD *)(*v36 + 8LL * v39) + 2 * v45) );
          v40 += v45 + 1;
          v38 += -1 - v45;
          ++v39;
        }
        while ( v39 < *((_DWORD *)v34 + 2) );
        *(_QWORD *)(a4 + 40) = v33;
        v33 = 0;
        *(_DWORD *)(a4 + 32) = 8210;
        *(_DWORD *)(a4 + 36) = 2 * v51;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids, v51);
      }
LABEL_66:
      CoTaskMemFree(v33);
    }
  }
  else
  {
    if ( v7 == 72 )
    {
      v47 = CoTaskMemAlloc(0x10u);
      *(_QWORD *)(a4 + 40) = v47;
      if ( v47 )
      {
        v16 = 0;
        *v47 = *(_OWORD *)*((_QWORD *)a2 + 1);
        *(_DWORD *)(a4 + 32) = 13;
        *(_DWORD *)(a4 + 36) = 16;
        return v16;
      }
      return (unsigned int)-2147024882;
    }
    if ( *a2 )
    {
      if ( v7 == 11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v46 = L"true";
          if ( a2[4] != 0xFFFF )
            v46 = (const wchar_t *)L"false";
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids, v46);
        }
        v18 = CoTaskMemAlloc(1u);
        *(_QWORD *)(a4 + 40) = v18;
        if ( v18 )
        {
          v16 = 0;
          *v18 = (a2[4] != 0xFFFF) - 1;
          *(_DWORD *)(a4 + 32) = 17;
          *(_DWORD *)(a4 + 36) = 1;
          return v16;
        }
        return (unsigned int)-2147024882;
      }
      if ( v7 == 19 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids,
            *((unsigned int *)a2 + 2));
        v20 = CoTaskMemAlloc(4u);
        *(_QWORD *)(a4 + 40) = v20;
        if ( v20 )
        {
          v16 = 0;
          *v20 = *((_DWORD *)a2 + 2);
          *(_DWORD *)(a4 + 32) = 7;
          *(_DWORD *)(a4 + 36) = 4;
          return v16;
        }
        return (unsigned int)-2147024882;
      }
      return (unsigned int)-2147467259;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids);
    *(_DWORD *)(a4 + 32) = 0;
    return 0;
  }
  return v16;
}

```

## disassembly

```asm
0x180006a80  mov     [rsp+arg_10], rbx
0x180006a85  mov     [rsp+arg_18], r9
0x180006a8a  mov     [rsp+arg_8], rdx
0x180006a8f  mov     [rsp+arg_0], rcx
0x180006a94  push    rbp
0x180006a95  push    rsi
0x180006a96  push    rdi
0x180006a97  push    r12
0x180006a99  push    r13
0x180006a9b  push    r14
0x180006a9d  push    r15
0x180006a9f  sub     rsp, 30h
0x180006aa3  xorps   xmm0, xmm0
0x180006aa6  mov     r14, r9
0x180006aa9  movups  xmmword ptr [r9], xmm0
0x180006aad  mov     esi, r8d
0x180006ab0  mov     r12, rdx
0x180006ab3  movups  xmmword ptr [r9+10h], xmm0
0x180006ab8  movups  xmmword ptr [r9+20h], xmm0
0x180006abd  movzx   ecx, word ptr [rdx]
0x180006ac0  cmp     ecx, 1Fh
0x180006ac3  jnz     loc_180006B61
0x180006ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad0  lea     rbp, WPP_GLOBAL_Control
0x180006ad7  cmp     rcx, rbp
0x180006ada  jnz     loc_180006C9F
0x180006ae0  mov     rbx, [r12+8]
0x180006ae5  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180006aec  test    rbx, rbx
0x180006aef  jz      loc_180007083
0x180006af5  mov     rax, r13
0x180006af8  nop     dword ptr [rax+rax+00000000h]
0x180006b00  cmp     word ptr [rbx+rax*2+2], 0
0x180006b06  lea     rax, [rax+1]
0x180006b0a  jnz     short loc_180006B00
0x180006b0c  lea     rdi, ds:2[rax*2]
0x180006b14  mov     rcx, rdi; cb
0x180006b17  call    cs:__imp_CoTaskMemAlloc
0x180006b1d  mov     r11, rax
0x180006b20  test    rax, rax
0x180006b23  jnz     loc_180006C60
0x180006b29  mov     r15d, 8007000Eh
0x180006b2f  test    r15d, r15d
0x180006b32  jns     loc_180006BE0
0x180006b38  test    r11, r11
0x180006b3b  jz      short loc_180006B46
0x180006b3d  mov     rcx, r11; pv
0x180006b40  call    cs:__imp_CoTaskMemFree
0x180006b46  mov     rbx, [rsp+68h+arg_10]
0x180006b4e  mov     eax, r15d
0x180006b51  add     rsp, 30h
0x180006b55  pop     r15
0x180006b57  pop     r14
0x180006b59  pop     r13
0x180006b5b  pop     r12
0x180006b5d  pop     rdi
0x180006b5e  pop     rsi
0x180006b5f  pop     rbp
0x180006b60  retn
0x180006b61  cmp     ecx, 48h ; 'H'
0x180006b64  ja      loc_180006CED
0x180006b6a  jz      loc_180006F99
0x180006b70  test    ecx, ecx
0x180006b72  jz      loc_180006CC8
0x180006b78  cmp     ecx, 0Bh
0x180006b7b  jnz     loc_180006C17
0x180006b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b88  lea     rbp, WPP_GLOBAL_Control
0x180006b8f  cmp     rcx, rbp
0x180006b92  jz      short loc_180006B9E
0x180006b94  test    byte ptr [rcx+1Ch], 1
0x180006b98  jnz     loc_180006F44
0x180006b9e  mov     ebx, 1
0x180006ba3  mov     ecx, ebx; cb
0x180006ba5  call    cs:__imp_CoTaskMemAlloc
0x180006bab  mov     [r14+28h], rax
0x180006baf  test    rax, rax
0x180006bb2  jz      loc_180006C55
0x180006bb8  xor     ecx, ecx
0x180006bba  cmp     word ptr [r12+8], 0FFFFh
0x180006bc1  mov     r15d, ecx
0x180006bc4  setnz   cl
0x180006bc7  dec     cl
0x180006bc9  mov     [rax], cl
0x180006bcb  mov     dword ptr [r14+20h], 11h
0x180006bd3  mov     [r14+24h], ebx
0x180006bd7  jmp     loc_180006B46
0x180006be0  cmp     word ptr [r11+r13*2+2], 0
0x180006be7  lea     r13, [r13+1]
0x180006beb  jnz     short loc_180006BE0
0x180006bed  lea     ecx, ds:2[r13*2]
0x180006bf5  mov     [r14+28h], r11
0x180006bf9  mov     [r14+24h], ecx
0x180006bfd  test    sil, 1
0x180006c01  mov     ecx, 19h
0x180006c06  mov     eax, 12h
0x180006c0b  cmovz   ecx, eax
0x180006c0e  mov     [r14+20h], ecx
0x180006c12  jmp     loc_180006B46
0x180006c17  cmp     ecx, 13h
0x180006c1a  jnz     loc_180006EF9
0x180006c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c27  lea     rbp, WPP_GLOBAL_Control
0x180006c2e  cmp     rcx, rbp
0x180006c31  jz      short loc_180006C3D
0x180006c33  test    byte ptr [rcx+1Ch], 1
0x180006c37  jnz     loc_180006F04
0x180006c3d  mov     ecx, 4; cb
0x180006c42  call    cs:__imp_CoTaskMemAlloc
0x180006c48  mov     [r14+28h], rax
0x180006c4c  test    rax, rax
0x180006c4f  jnz     loc_180006F23
0x180006c55  mov     r15d, 8007000Eh
0x180006c5b  jmp     loc_180006B46
0x180006c60  shr     rdi, 1
0x180006c63  mov     rdx, rdi; cchDest
0x180006c66  call    StringValidateDestW
0x180006c6b  mov     r15d, eax
0x180006c6e  test    eax, eax
0x180006c70  js      loc_18000706F
0x180006c76  mov     r9, rbx; pszSrc
0x180006c79  mov     rcx, r11; pszDest
0x180006c7c  call    StringCopyWorkerW_0
0x180006c81  mov     r15d, eax
0x180006c84  test    eax, eax
0x180006c86  jz      loc_180006B2F
0x180006c8c  xor     ebx, ebx
0x180006c8e  mov     rcx, r11; pv
0x180006c91  call    cs:__imp_CoTaskMemFree
0x180006c97  mov     r11, rbx
0x180006c9a  jmp     loc_180006B2F
0x180006c9f  test    byte ptr [rcx+1Ch], 1
0x180006ca3  jz      loc_180006AE0
0x180006ca9  mov     r9, [r12+8]
0x180006cae  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006cb5  mov     rcx, [rcx+10h]
0x180006cb9  mov     edx, 11h
0x180006cbe  call    WPP_SF_S
0x180006cc3  jmp     loc_180006AE0
0x180006cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ccf  lea     rbp, WPP_GLOBAL_Control
0x180006cd6  cmp     rcx, rbp
0x180006cd9  jnz     loc_180006F75
0x180006cdf  xor     eax, eax
0x180006ce1  mov     [r14+20h], eax
0x180006ce5  mov     r15d, eax
0x180006ce8  jmp     loc_180006B46
0x180006ced  sub     ecx, 1011h
0x180006cf3  jz      loc_180006FF2
0x180006cf9  cmp     ecx, 0Eh
0x180006cfc  jnz     loc_180006EF9
0x180006d02  mov     r8d, [rdx+8]
0x180006d06  xor     r14d, r14d
0x180006d09  mov     ebp, 1
0x180006d0e  mov     r15d, 80004005h
0x180006d14  mov     [rsp+68h+arg_0], rbp
0x180006d19  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180006d20  test    r8d, r8d
0x180006d23  jz      short loc_180006D5A
0x180006d25  mov     r9, [r12+10h]
0x180006d2a  mov     edx, r14d
0x180006d2d  nop     dword ptr [rax]
0x180006d30  mov     eax, edx
0x180006d32  mov     rcx, [r9+rax*8]
0x180006d36  mov     rax, r13
0x180006d39  nop     dword ptr [rax+00000000h]
0x180006d40  inc     rax
0x180006d43  cmp     [rcx+rax*2], r14w
0x180006d48  jnz     short loc_180006D40
0x180006d4a  inc     ebp
0x180006d4c  inc     edx
0x180006d4e  add     ebp, eax
0x180006d50  cmp     edx, r8d
0x180006d53  jb      short loc_180006D30
0x180006d55  mov     [rsp+68h+arg_0], rbp
0x180006d5a  movsxd  rdi, ebp
0x180006d5d  mov     ebx, 10h
0x180006d62  mov     rsi, r12
0x180006d65  lea     rcx, [rdi+rdi]; cb
0x180006d69  call    cs:__imp_CoTaskMemAlloc
0x180006d6f  mov     r12, rax
0x180006d72  test    rax, rax
0x180006d75  jz      loc_180006B46
0x180006d7b  mov     rdx, [rsp+68h+arg_8]
0x180006d80  mov     [rax+rdi*2-2], r14w
0x180006d86  cmp     [rdx+8], r14d
0x180006d8a  jbe     loc_180006EB3
0x180006d90  mov     r8, [rbx+rsi]
0x180006d94  lea     r14, [rbx+rsi]
0x180006d98  mov     r10, cs:WPP_GLOBAL_Control
0x180006d9f  xor     ecx, ecx
0x180006da1  mov     ebx, ebp
0x180006da3  mov     edi, ecx
0x180006da5  lea     rbp, WPP_GLOBAL_Control
0x180006dac  mov     rsi, rax
0x180006daf  nop
0x180006db0  cmp     r10, rbp
0x180006db3  jnz     loc_180006EC1
0x180006db9  mov     r11d, edi
0x180006dbc  movsxd  r8, ebx
0x180006dbf  test    ebx, ebx
0x180006dc1  jz      loc_180006FD4
0x180006dc7  cmp     r8, 7FFFFFFFh
0x180006dce  ja      loc_180006FE2
0x180006dd4  mov     rax, [rdx+10h]
0x180006dd8  xor     r10d, r10d
0x180006ddb  mov     ecx, 7FFFFFFEh
0x180006de0  mov     r9, rsi
0x180006de3  mov     r15d, r10d
0x180006de6  mov     rdx, [rax+r11*8]
0x180006dea  nop     word ptr [rax+rax+00h]
0x180006df0  test    rcx, rcx
0x180006df3  jz      short loc_180006E23
0x180006df5  movzx   eax, word ptr [rdx]
0x180006df8  test    ax, ax
0x180006dfb  jz      short loc_180006E1E
0x180006dfd  mov     [r9], ax
0x180006e01  add     rdx, 2
0x180006e05  add     r9, 2
0x180006e09  dec     rcx
0x180006e0c  sub     r8, 1
0x180006e10  jnz     short loc_180006DF0
0x180006e12  sub     r9, 2
0x180006e16  mov     r15d, 8007007Ah
0x180006e1c  jmp     short loc_180006E23
0x180006e1e  test    r8, r8
0x180006e21  jz      short loc_180006E12
0x180006e23  mov     rdx, [rsp+68h+arg_8]
0x180006e28  mov     [r9], r10w
0x180006e2c  mov     r10, cs:WPP_GLOBAL_Control
0x180006e33  test    r15d, r15d
0x180006e36  js      short loc_180006EB3
0x180006e38  mov     r8, [r14]
0x180006e3b  mov     rcx, r13
0x180006e3e  mov     rax, [r8+r11*8]
0x180006e42  inc     rcx
0x180006e45  cmp     word ptr [rax+rcx*2], 0
0x180006e4a  jnz     short loc_180006E42
0x180006e4c  mov     eax, r13d
0x180006e4f  lea     rsi, [rsi+rcx*2]
0x180006e53  sub     eax, ecx
0x180006e55  add     rsi, 2
0x180006e59  add     ebx, eax
0x180006e5b  inc     edi
0x180006e5d  cmp     edi, [rdx+8]
0x180006e60  jb      loc_180006DB0
0x180006e66  mov     rdx, [rsp+68h+arg_18]
0x180006e6e  xor     ecx, ecx
0x180006e70  mov     rbx, [rsp+68h+arg_0]
0x180006e75  mov     [rdx+28h], r12
0x180006e79  mov     r12d, ecx
0x180006e7c  lea     eax, [rbx+rbx]
0x180006e7f  mov     dword ptr [rdx+20h], 2012h
0x180006e86  mov     [rdx+24h], eax
0x180006e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e90  cmp     rcx, rbp
0x180006e93  jz      short loc_180006EB3
0x180006e95  test    byte ptr [rcx+1Ch], 1
0x180006e99  jz      short loc_180006EB3
0x180006e9b  mov     rcx, [rcx+10h]
0x180006e9f  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006ea6  mov     edx, 17h
0x180006eab  mov     r9d, ebx
0x180006eae  call    WPP_SF_d
0x180006eb3  mov     rcx, r12; pv
0x180006eb6  call    cs:__imp_CoTaskMemFree
0x180006ebc  jmp     loc_180006B46
0x180006ec1  test    byte ptr [r10+1Ch], 1
0x180006ec6  jz      loc_180006DB9
0x180006ecc  mov     rcx, [r10+10h]
0x180006ed0  mov     edx, 16h
0x180006ed5  mov     r9d, edi
0x180006ed8  mov     r9, [r8+r9*8]
0x180006edc  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006ee3  call    WPP_SF_S
0x180006ee8  mov     r10, cs:WPP_GLOBAL_Control
0x180006eef  mov     rdx, [rsp+68h+arg_8]
0x180006ef4  jmp     loc_180006DB9
0x180006ef9  mov     r15d, 80004005h
0x180006eff  jmp     loc_180006B46
0x180006f04  mov     r9d, [r12+8]
0x180006f09  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006f10  mov     rcx, [rcx+10h]
0x180006f14  mov     edx, 12h
0x180006f19  call    WPP_SF_d
0x180006f1e  jmp     loc_180006C3D
0x180006f23  xor     ecx, ecx
0x180006f25  mov     r15d, ecx
0x180006f28  mov     ecx, [r12+8]
0x180006f2d  mov     [rax], ecx
0x180006f2f  mov     dword ptr [r14+20h], 7
0x180006f37  mov     dword ptr [r14+24h], 4
0x180006f3f  jmp     loc_180006B46
0x180006f44  cmp     word ptr [rdx+8], 0FFFFh
0x180006f49  lea     rax, aFalse; "false"
0x180006f50  mov     rcx, [rcx+10h]
0x180006f54  lea     r9, aTrue; "true"
0x180006f5b  cmovnz  r9, rax
0x180006f5f  lea     r8, WPP_81c79e6b29ca30ffa466dc55c7bf2d12_Traceguids
0x180006f66  mov     edx, 14h
  ... truncated ...
```
