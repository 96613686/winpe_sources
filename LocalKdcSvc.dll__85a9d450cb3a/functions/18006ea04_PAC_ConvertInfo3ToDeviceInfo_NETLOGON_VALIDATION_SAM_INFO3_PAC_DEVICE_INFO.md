# PAC_ConvertInfo3ToDeviceInfo(_NETLOGON_VALIDATION_SAM_INFO3 *,_PAC_DEVICE_INFO * *)

- ea: `0x18006ea04`
- end: `0x18006eff7`
- name: `?PAC_ConvertInfo3ToDeviceInfo@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAU_PAC_DEVICE_INFO@@@Z`
- size: `1523`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, struct _PAC_DEVICE_INFO **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007006c`
- `0x180071134`

## callees

- `0x1800038f0`
- `0x18005a060`
- `0x18005a090`
- `0x18006ea04`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18006eb07`
- `ntdll!RtlSubAuthoritySid` at `0x18006eeec`
- `ntdll!RtlSubAuthoritySid` at `0x18006eb07`
- `ntdll!RtlSubAuthoritySid` at `0x18006eeec`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006eaf1`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006ee59`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006ee96`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006eaf1`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006ee59`
- `ntdll!RtlSubAuthorityCountSid` at `0x18006ee96`
- `ntdll!RtlLengthSid` at `0x18006ea3d`
- `ntdll!RtlLengthSid` at `0x18006ebac`
- `ntdll!RtlLengthSid` at `0x18006ec99`
- `ntdll!RtlLengthSid` at `0x18006ecb6`
- `ntdll!RtlLengthSid` at `0x18006ed2d`
- `ntdll!RtlLengthSid` at `0x18006ed4a`
- `ntdll!RtlLengthSid` at `0x18006ee6e`
- `ntdll!RtlLengthSid` at `0x18006ee89`
- `ntdll!RtlLengthSid` at `0x18006ef8b`
- `ntdll!RtlLengthSid` at `0x18006efa6`
- `ntdll!RtlLengthSid` at `0x18006ea3d`
- `ntdll!RtlLengthSid` at `0x18006ebac`
- `ntdll!RtlLengthSid` at `0x18006ec99`
- `ntdll!RtlLengthSid` at `0x18006ecb6`
- `ntdll!RtlLengthSid` at `0x18006ed2d`
- `ntdll!RtlLengthSid` at `0x18006ed4a`
- `ntdll!RtlLengthSid` at `0x18006ee6e`
- `ntdll!RtlLengthSid` at `0x18006ee89`
- `ntdll!RtlLengthSid` at `0x18006ef8b`
- `ntdll!RtlLengthSid` at `0x18006efa6`
- `ntdll!RtlCopySid` at `0x18006eca7`
- `ntdll!RtlCopySid` at `0x18006ed3b`
- `ntdll!RtlCopySid` at `0x18006ee7c`
- `ntdll!RtlCopySid` at `0x18006ef99`
- `ntdll!RtlCopySid` at `0x18006eca7`
- `ntdll!RtlCopySid` at `0x18006ed3b`
- `ntdll!RtlCopySid` at `0x18006ee7c`
- `ntdll!RtlCopySid` at `0x18006ef99`
- `ntdll!RtlLengthRequiredSid` at `0x18006ebfb`
- `ntdll!RtlLengthRequiredSid` at `0x18006ebfb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18006eac5`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18006eac5`
- `ntdll!RtlEqualPrefixSid` at `0x18006eb42`
- `ntdll!RtlEqualPrefixSid` at `0x18006edf0`
- `ntdll!RtlEqualPrefixSid` at `0x18006eb42`
- `ntdll!RtlEqualPrefixSid` at `0x18006edf0`
- `ntdll!RtlValidSid` at `0x18006eab2`
- `ntdll!RtlValidSid` at `0x18006eb25`
- `ntdll!RtlValidSid` at `0x18006eab2`
- `ntdll!RtlValidSid` at `0x18006eb25`

## pseudocode

```c
__int64 __fastcall PAC_ConvertInfo3ToDeviceInfo(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        struct _PAC_DEVICE_INFO **a2)
{
  _DWORD *v3; // r15
  __int64 v4; // r13
  ULONG v5; // esi
  unsigned int v6; // eax
  PSID *v7; // rax
  PSID *v8; // rbp
  NTSTATUS v9; // ebx
  unsigned int v10; // r12d
  unsigned int i; // ebx
  PSID_IDENTIFIER_AUTHORITY v12; // rax
  int v13; // ecx
  unsigned int j; // edi
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  int v17; // eax
  size_t v18; // rcx
  _DWORD *v19; // rax
  char *v20; // rsi
  char *v21; // rdi
  void *v22; // rbx
  ULONG v23; // eax
  ULONG v24; // eax
  unsigned int v25; // r8d
  char *v26; // r13
  __int64 v27; // rdi
  __int64 v28; // r9
  void *v29; // rbx
  ULONG v30; // eax
  ULONG v31; // eax
  __int64 v32; // r8
  __int64 v33; // rdx
  unsigned int v34; // ecx
  unsigned int k; // eax
  __int64 v36; // rsi
  __int64 v37; // rsi
  __int64 v38; // rdi
  PUCHAR v39; // rax
  PSID v40; // rbx
  void *v41; // rdi
  ULONG v42; // eax
  PUCHAR v43; // rax
  __int64 v44; // rsi
  PULONG v45; // rax
  int v46; // eax
  unsigned int v47; // esi
  __int64 v48; // rdx
  PSID v49; // rbx
  ULONG v50; // eax
  ULONG v51; // eax
  unsigned int v53; // [rsp+20h] [rbp-78h]
  unsigned int v54; // [rsp+24h] [rbp-74h]
  __int64 v55; // [rsp+28h] [rbp-70h]
  __int64 v56; // [rsp+30h] [rbp-68h]
  __int64 v57; // [rsp+38h] [rbp-60h]
  __int64 v58; // [rsp+40h] [rbp-58h]
  unsigned int v59; // [rsp+A0h] [rbp+8h]
  unsigned int v61; // [rsp+B0h] [rbp+18h]
  int v62; // [rsp+B8h] [rbp+20h]

  v3 = 0;
  v4 = 0;
  v62 = 0;
  v5 = RtlLengthSid(*((PSID *)a1 + 28)) + 8 * (*((_DWORD *)a1 + 39) + 8);
  v6 = *((_DWORD *)a1 + 68);
  if ( v6 )
  {
    v7 = (PSID *)MIDL_user_allocate(16LL * v6);
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-1073741670;
    memcpy_0(v7, *((const void **)a1 + 35), 16LL * *((unsigned int *)a1 + 68));
    v10 = *((_DWORD *)a1 + 68);
    for ( i = 0; i < v10; ++i )
    {
      if ( !RtlValidSid(v8[2 * i]) )
      {
LABEL_22:
        v9 = -1073741811;
        goto LABEL_59;
      }
      v12 = RtlIdentifierAuthoritySid(v8[2 * i]);
      v13 = *(_DWORD *)v12->Value;
      if ( !*(_DWORD *)v12->Value )
        v13 = *(unsigned __int16 *)&v12->Value[4] - 1280;
      if ( !v13 && *RtlSubAuthorityCountSid(v8[2 * i]) == 5 && *RtlSubAuthoritySid(v8[2 * i], 0) == 21 )
      {
        for ( j = i + 1; j < v10; ++j )
        {
          if ( !RtlValidSid(v8[2 * j]) )
            goto LABEL_22;
          if ( RtlEqualPrefixSid(v8[2 * i], v8[2 * j]) )
          {
            if ( ++i != j )
            {
              v15 = *(_OWORD *)&v8[2 * j];
              *(_OWORD *)&v8[2 * j] = *(_OWORD *)&v8[2 * i];
              *(_OWORD *)&v8[2 * i] = v15;
            }
          }
        }
        v4 = (unsigned int)++v62;
      }
      else
      {
        v16 = *(_OWORD *)&v8[2 * i];
        *(_OWORD *)&v8[2 * i] = *(_OWORD *)&v8[2 * --v10];
        *(_OWORD *)&v8[2 * v10] = v16;
        v5 += RtlLengthSid(v8[2 * v10]);
        --i;
      }
    }
    v5 += 8 * (2 * *((_DWORD *)a1 + 68) - v10);
  }
  else
  {
    v8 = 0;
    v10 = 0;
  }
  v17 = *((_DWORD *)a1 + 74);
  if ( v17 )
  {
    v4 = (unsigned int)(v4 + 1);
    v5 += 8 * v17;
    v62 = v4;
  }
  v18 = v5 + (_DWORD)v4 * (RtlLengthRequiredSid(4u) + 24);
  if ( (unsigned int)v18 > 0xFFFF )
  {
    v9 = -1073741637;
    goto LABEL_58;
  }
  v19 = MIDL_user_allocate(v18);
  v3 = v19;
  if ( !v19 )
  {
    v9 = -1073741670;
    goto LABEL_58;
  }
  v20 = (char *)(v19 + 16);
  v58 = (__int64)&v19[6 * v4 + 16];
  v55 = v58 + 16LL * (*((_DWORD *)a1 + 68) - v10);
  v21 = (char *)(v55 + 8LL * (v10 + *((_DWORD *)a1 + 74) + *((_DWORD *)a1 + 39)));
  *v19 = *((_DWORD *)a1 + 37);
  v19[1] = *((_DWORD *)a1 + 38);
  *((_QWORD *)v19 + 1) = v21;
  v22 = (void *)*((_QWORD *)a1 + 28);
  v23 = RtlLengthSid(v22);
  v9 = RtlCopySid(v23, v21, v22);
  v24 = RtlLengthSid(*((PSID *)a1 + 28));
  if ( v9 >= 0 )
  {
    v25 = 0;
    v26 = &v21[v24];
    v27 = *((unsigned int *)a1 + 39);
    v28 = 0;
    v59 = 0;
    v61 = v27;
    v3[4] = v27;
    for ( *((_QWORD *)v3 + 3) = v55; (unsigned int)v28 < v3[4]; v28 = (unsigned int)(v28 + 1) )
      *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v28) = *(_QWORD *)(*((_QWORD *)a1 + 20) + 8 * v28);
    if ( *((_DWORD *)a1 + 74) )
    {
      *(_QWORD *)v20 = v26;
      v29 = (void *)*((_QWORD *)a1 + 36);
      v30 = RtlLengthSid(v29);
      v9 = RtlCopySid(v30, v26, v29);
      v31 = RtlLengthSid(*((PSID *)a1 + 36));
      if ( v9 < 0 )
        goto LABEL_58;
      v32 = 0;
      v26 += v31;
      *((_DWORD *)v20 + 2) = *((_DWORD *)a1 + 74);
      *((_QWORD *)v20 + 2) = v55 + 8 * v27;
      if ( *((_DWORD *)a1 + 74) )
      {
        do
        {
          *(_QWORD *)(*((_QWORD *)v20 + 2) + 8 * v32) = *(_QWORD *)(*((_QWORD *)a1 + 38) + 8 * v32);
          v32 = (unsigned int)(v32 + 1);
        }
        while ( (unsigned int)v32 < *((_DWORD *)a1 + 74) );
      }
      LODWORD(v27) = v32 + v27;
      v25 = 1;
      v59 = 1;
      v61 = v27;
    }
    v33 = v55;
    v34 = 0;
    v54 = 0;
    for ( k = 0; ; k = v53 + 1 )
    {
      v53 = k;
      if ( k >= v10 )
      {
        if ( v62 )
        {
          v3[12] = v62;
          *((_QWORD *)v3 + 7) = v3 + 16;
        }
        if ( v8 )
        {
          v46 = *((_DWORD *)a1 + 68);
          if ( v10 != v46 )
          {
            v3[8] = v46 - v10;
            v47 = 0;
            *((_QWORD *)v3 + 5) = v58;
            while ( v10 < *((_DWORD *)a1 + 68) )
            {
              v48 = 2LL * v47;
              *(_DWORD *)(*((_QWORD *)v3 + 5) + 8 * v48 + 8) = v8[2 * v10 + 1];
              *(_QWORD *)(*((_QWORD *)v3 + 5) + 8 * v48) = v26;
              v49 = v8[2 * v10];
              v50 = RtlLengthSid(v49);
              v9 = RtlCopySid(v50, v26, v49);
              v51 = RtlLengthSid(v8[2 * v10]);
              if ( v9 < 0 )
                goto LABEL_59;
              ++v47;
              v26 += v51;
              ++v10;
            }
          }
        }
        *a2 = (struct _PAC_DEVICE_INFO *)v3;
        v3 = 0;
        break;
      }
      if ( k )
      {
        v36 = k;
        v57 = k;
        if ( RtlEqualPrefixSid(v8[2 * k], v8[2 * v34]) )
        {
          v56 = (unsigned int)v27;
          goto LABEL_48;
        }
        v33 = v55;
        v25 = ++v59;
      }
      else
      {
        v36 = 0;
        v57 = 0;
      }
      v37 = 2 * v36;
      v38 = 3LL * v25;
      v56 = v61;
      *(_QWORD *)&v3[2 * v38 + 16] = v26;
      v3[2 * v38 + 18] = 0;
      *(_QWORD *)&v3[2 * v38 + 20] = v33 + 8LL * v61;
      v39 = RtlSubAuthorityCountSid(v8[v37]);
      --*v39;
      v40 = v8[v37];
      v41 = *(void **)&v3[2 * v38 + 16];
      v42 = RtlLengthSid(v40);
      v9 = RtlCopySid(v42, v41, v40);
      v27 = RtlLengthSid(v8[v37]);
      v43 = RtlSubAuthorityCountSid(v8[v37]);
      ++*v43;
      if ( v9 < 0 )
        break;
      v26 += v27;
      LODWORD(v27) = v61;
      v36 = v57;
      v54 = v53;
LABEL_48:
      v44 = 2 * v36;
      ++v3[6 * v59 + 18];
      *(_DWORD *)(v55 + 8 * v56 + 4) = v8[v44 + 1];
      v45 = RtlSubAuthoritySid(v8[v44], 4u);
      v33 = v55;
      LODWORD(v27) = v27 + 1;
      v25 = v59;
      v61 = v27;
      *(_DWORD *)(v55 + 8 * v56) = *v45;
      v34 = v54;
    }
  }
LABEL_58:
  if ( v8 )
LABEL_59:
    MIDL_user_free(v8);
  if ( v3 )
    MIDL_user_free(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006ea04  mov     rax, rsp
0x18006ea07  mov     [rax+10h], rdx
0x18006ea0b  push    rbx
0x18006ea0c  push    rbp
0x18006ea0d  push    rsi
0x18006ea0e  push    rdi
0x18006ea0f  push    r12
0x18006ea11  push    r13
0x18006ea13  push    r14
0x18006ea15  push    r15
0x18006ea17  sub     rsp, 58h
0x18006ea1b  mov     r14, rcx
0x18006ea1e  mov     word ptr [rax+0Ch], 500h
0x18006ea24  mov     rcx, [rcx+0E0h]; Sid
0x18006ea2b  xor     r15d, r15d
0x18006ea2e  xor     r13d, r13d
0x18006ea31  mov     [rax+8], r15d
0x18006ea35  mov     [rsp+98h+arg_18], r13d
0x18006ea3d  call    cs:__imp_RtlLengthSid
0x18006ea43  mov     esi, [r14+9Ch]
0x18006ea4a  add     esi, 8
0x18006ea4d  lea     esi, [rax+rsi*8]
0x18006ea50  mov     eax, [r14+110h]
0x18006ea57  test    eax, eax
0x18006ea59  jz      loc_18006EBD8
0x18006ea5f  mov     ecx, eax
0x18006ea61  shl     rcx, 4; size
0x18006ea65  call    MIDL_user_allocate
0x18006ea6a  mov     rbp, rax
0x18006ea6d  test    rax, rax
0x18006ea70  jnz     short loc_18006EA7C
0x18006ea72  mov     ebx, 0C000009Ah
0x18006ea77  jmp     loc_18006EFE4
0x18006ea7c  mov     r8d, [r14+110h]
0x18006ea83  mov     rcx, rbp; void *
0x18006ea86  mov     rdx, [r14+118h]; Src
0x18006ea8d  shl     r8, 4; Size
0x18006ea91  call    memcpy_0
0x18006ea96  mov     r12d, [r14+110h]
0x18006ea9d  xor     ebx, ebx
0x18006ea9f  cmp     ebx, r12d
0x18006eaa2  jnb     loc_18006EBC7
0x18006eaa8  mov     edi, ebx
0x18006eaaa  add     rdi, rdi
0x18006eaad  mov     rcx, [rbp+rdi*8+0]; Sid
0x18006eab2  call    cs:__imp_RtlValidSid
0x18006eab8  test    al, al
0x18006eaba  jz      loc_18006EBBD
0x18006eac0  mov     rcx, [rbp+rdi*8+0]; Sid
0x18006eac5  call    cs:__imp_RtlIdentifierAuthoritySid
0x18006eacb  mov     ecx, [rax]
0x18006eacd  sub     ecx, [rsp+98h+arg_0]
0x18006ead4  jnz     short loc_18006EAE4
0x18006ead6  movzx   ecx, word ptr [rax+4]
0x18006eada  movzx   eax, [rsp+98h+arg_4]
0x18006eae2  sub     ecx, eax
0x18006eae4  test    ecx, ecx
0x18006eae6  jnz     loc_18006EB88
0x18006eaec  mov     rcx, [rbp+rdi*8+0]; Sid
0x18006eaf1  call    cs:__imp_RtlSubAuthorityCountSid
0x18006eaf7  cmp     byte ptr [rax], 5
0x18006eafa  jnz     loc_18006EB88
0x18006eb00  mov     rcx, [rbp+rdi*8+0]; Sid
0x18006eb05  xor     edx, edx; SubAuthority
0x18006eb07  call    cs:__imp_RtlSubAuthoritySid
0x18006eb0d  cmp     dword ptr [rax], 15h
0x18006eb10  jnz     short loc_18006EB88
0x18006eb12  lea     edi, [rbx+1]
0x18006eb15  cmp     edi, r12d
0x18006eb18  jnb     short loc_18006EB73
0x18006eb1a  mov     r13d, edi
0x18006eb1d  add     r13, r13
0x18006eb20  mov     rcx, [rbp+r13*8+0]; Sid
0x18006eb25  call    cs:__imp_RtlValidSid
0x18006eb2b  test    al, al
0x18006eb2d  jz      loc_18006EBBD
0x18006eb33  mov     rdx, [rbp+r13*8+0]; Sid2
0x18006eb38  mov     ecx, ebx
0x18006eb3a  add     rcx, rcx
0x18006eb3d  mov     rcx, [rbp+rcx*8+0]; Sid1
0x18006eb42  call    cs:__imp_RtlEqualPrefixSid
0x18006eb48  test    al, al
0x18006eb4a  jz      short loc_18006EB6F
0x18006eb4c  inc     ebx
0x18006eb4e  cmp     ebx, edi
0x18006eb50  jz      short loc_18006EB6F
0x18006eb52  movups  xmm1, xmmword ptr [rbp+r13*8+0]
0x18006eb58  mov     eax, ebx
0x18006eb5a  add     rax, rax
0x18006eb5d  movups  xmm0, xmmword ptr [rbp+rax*8+0]
0x18006eb62  movdqu  xmmword ptr [rbp+r13*8+0], xmm0
0x18006eb69  movdqu  xmmword ptr [rbp+rax*8+0], xmm1
0x18006eb6f  inc     edi
0x18006eb71  jmp     short loc_18006EB15
0x18006eb73  mov     r13d, [rsp+98h+arg_18]
0x18006eb7b  inc     r13d
0x18006eb7e  mov     [rsp+98h+arg_18], r13d
0x18006eb86  jmp     short loc_18006EBB6
0x18006eb88  movups  xmm1, xmmword ptr [rbp+rdi*8+0]
0x18006eb8d  dec     r12d
0x18006eb90  mov     ecx, r12d
0x18006eb93  add     rcx, rcx
0x18006eb96  movups  xmm0, xmmword ptr [rbp+rcx*8+0]
0x18006eb9b  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18006eba1  movdqu  xmmword ptr [rbp+rcx*8+0], xmm1
0x18006eba7  mov     rcx, [rbp+rcx*8+0]; Sid
0x18006ebac  call    cs:__imp_RtlLengthSid
0x18006ebb2  add     esi, eax
0x18006ebb4  dec     ebx
0x18006ebb6  inc     ebx
0x18006ebb8  jmp     loc_18006EA9F
0x18006ebbd  mov     ebx, 0C000000Dh
0x18006ebc2  jmp     loc_18006EFCF
0x18006ebc7  mov     eax, [r14+110h]
0x18006ebce  add     eax, eax
0x18006ebd0  sub     eax, r12d
0x18006ebd3  lea     esi, [rsi+rax*8]
0x18006ebd6  jmp     short loc_18006EBDD
0x18006ebd8  xor     ebp, ebp
0x18006ebda  xor     r12d, r12d
0x18006ebdd  mov     eax, [r14+128h]
0x18006ebe4  test    eax, eax
0x18006ebe6  jz      short loc_18006EBF6
0x18006ebe8  inc     r13d
0x18006ebeb  lea     esi, [rsi+rax*8]
0x18006ebee  mov     [rsp+98h+arg_18], r13d
0x18006ebf6  mov     ecx, 4; SubAuthorityCount
0x18006ebfb  call    cs:__imp_RtlLengthRequiredSid
0x18006ec01  lea     ecx, [rax+18h]
0x18006ec04  imul    ecx, r13d
0x18006ec08  add     ecx, esi; size
0x18006ec0a  cmp     ecx, 0FFFFh
0x18006ec10  jbe     short loc_18006EC1C
0x18006ec12  mov     ebx, 0C00000BBh
0x18006ec17  jmp     loc_18006EFCA
0x18006ec1c  call    MIDL_user_allocate
0x18006ec21  mov     r15, rax
0x18006ec24  test    rax, rax
0x18006ec27  jnz     short loc_18006EC33
0x18006ec29  mov     ebx, 0C000009Ah
0x18006ec2e  jmp     loc_18006EFCA
0x18006ec33  lea     rsi, [rax+40h]
0x18006ec37  mov     eax, [r14+9Ch]
0x18006ec3e  add     eax, [r14+128h]
0x18006ec45  lea     rcx, ds:0[r13*2]
0x18006ec4d  add     rcx, r13
0x18006ec50  add     eax, r12d
0x18006ec53  lea     rdx, [rsi+rcx*8]
0x18006ec57  mov     ecx, [r14+110h]
0x18006ec5e  sub     ecx, r12d
0x18006ec61  mov     [rsp+98h+var_58], rdx
0x18006ec66  shl     rcx, 4
0x18006ec6a  add     rcx, rdx
0x18006ec6d  mov     [rsp+98h+var_70], rcx
0x18006ec72  lea     rdi, [rcx+rax*8]
0x18006ec76  mov     eax, [r14+94h]
0x18006ec7d  mov     [r15], eax
0x18006ec80  mov     eax, [r14+98h]
0x18006ec87  mov     [r15+4], eax
0x18006ec8b  mov     [r15+8], rdi
0x18006ec8f  mov     rbx, [r14+0E0h]
0x18006ec96  mov     rcx, rbx; Sid
0x18006ec99  call    cs:__imp_RtlLengthSid
0x18006ec9f  mov     r8, rbx; SourceSid
0x18006eca2  mov     rdx, rdi; DestinationSid
0x18006eca5  mov     ecx, eax; DestinationSidLength
0x18006eca7  call    cs:__imp_RtlCopySid
0x18006ecad  mov     rcx, [r14+0E0h]; Sid
0x18006ecb4  mov     ebx, eax
0x18006ecb6  call    cs:__imp_RtlLengthSid
0x18006ecbc  test    ebx, ebx
0x18006ecbe  js      loc_18006EFCA
0x18006ecc4  mov     r13d, eax
0x18006ecc7  xor     r8d, r8d
0x18006ecca  mov     rax, [rsp+98h+var_70]
0x18006eccf  add     r13, rdi
0x18006ecd2  mov     edi, [r14+9Ch]
0x18006ecd9  xor     r9d, r9d
0x18006ecdc  mov     [rsp+98h+arg_0], r8d
0x18006ece4  mov     [rsp+98h+arg_10], edi
0x18006eceb  mov     [r15+10h], edi
0x18006ecef  mov     [r15+18h], rax
0x18006ecf3  test    edi, edi
0x18006ecf5  jz      short loc_18006ED13
0x18006ecf7  mov     rax, [r14+0A0h]
0x18006ecfe  mov     rcx, [r15+18h]
0x18006ed02  mov     rax, [rax+r9*8]
0x18006ed06  mov     [rcx+r9*8], rax
0x18006ed0a  inc     r9d
0x18006ed0d  cmp     r9d, [r15+10h]
0x18006ed11  jb      short loc_18006ECF7
0x18006ed13  cmp     [r14+128h], r8d
0x18006ed1a  jz      loc_18006EDB7
0x18006ed20  mov     [rsi], r13
0x18006ed23  mov     rbx, [r14+120h]
0x18006ed2a  mov     rcx, rbx; Sid
0x18006ed2d  call    cs:__imp_RtlLengthSid
0x18006ed33  mov     r8, rbx; SourceSid
0x18006ed36  mov     rdx, r13; DestinationSid
0x18006ed39  mov     ecx, eax; DestinationSidLength
0x18006ed3b  call    cs:__imp_RtlCopySid
0x18006ed41  mov     rcx, [r14+120h]; Sid
0x18006ed48  mov     ebx, eax
0x18006ed4a  call    cs:__imp_RtlLengthSid
0x18006ed50  test    ebx, ebx
0x18006ed52  js      loc_18006EFCA
0x18006ed58  mov     rcx, [rsp+98h+var_70]
0x18006ed5d  xor     r8d, r8d
0x18006ed60  mov     eax, eax
0x18006ed62  add     r13, rax
0x18006ed65  mov     eax, [r14+128h]
0x18006ed6c  mov     [rsi+8], eax
0x18006ed6f  lea     rax, [rcx+rdi*8]
0x18006ed73  mov     [rsi+10h], rax
0x18006ed77  cmp     [r14+128h], r8d
0x18006ed7e  jbe     short loc_18006ED9F
0x18006ed80  mov     rax, [r14+130h]
0x18006ed87  mov     rcx, [rsi+10h]
0x18006ed8b  mov     rax, [rax+r8*8]
0x18006ed8f  mov     [rcx+r8*8], rax
0x18006ed93  inc     r8d
0x18006ed96  cmp     r8d, [r14+128h]
0x18006ed9d  jb      short loc_18006ED80
0x18006ed9f  add     edi, r8d
0x18006eda2  mov     r8d, 1
0x18006eda8  mov     [rsp+98h+arg_0], r8d
0x18006edb0  mov     [rsp+98h+arg_10], edi
0x18006edb7  mov     rdx, [rsp+98h+var_70]
0x18006edbc  xor     ecx, ecx
0x18006edbe  mov     [rsp+98h+var_74], ecx
0x18006edc2  xor     eax, eax
0x18006edc4  mov     [rsp+98h+var_78], eax
0x18006edc8  cmp     eax, r12d
0x18006edcb  jnb     loc_18006EF21
0x18006edd1  test    eax, eax
0x18006edd3  jz      short loc_18006EE20
0x18006edd5  mov     edx, ecx
0x18006edd7  mov     ecx, eax
0x18006edd9  add     rdx, rdx
0x18006eddc  add     rcx, rcx
0x18006eddf  mov     esi, eax
0x18006ede1  mov     [rsp+98h+var_60], rsi
0x18006ede6  mov     rdx, [rbp+rdx*8+0]; Sid2
0x18006edeb  mov     rcx, [rbp+rcx*8+0]; Sid1
0x18006edf0  call    cs:__imp_RtlEqualPrefixSid
0x18006edf6  test    al, al
0x18006edf8  jnz     short loc_18006EE14
0x18006edfa  mov     r8d, [rsp+98h+arg_0]
0x18006ee02  mov     rdx, [rsp+98h+var_70]
0x18006ee07  inc     r8d
0x18006ee0a  mov     [rsp+98h+arg_0], r8d
0x18006ee12  jmp     short loc_18006EE27
0x18006ee14  mov     eax, edi
0x18006ee16  mov     [rsp+98h+var_68], rax
0x18006ee1b  jmp     loc_18006EEBD
0x18006ee20  xor     esi, esi
0x18006ee22  mov     [rsp+98h+var_60], rsi
0x18006ee27  mov     eax, r8d
0x18006ee2a  add     rsi, rsi
0x18006ee2d  lea     rdi, [rax+rax*2]
0x18006ee31  mov     eax, [rsp+98h+arg_10]
0x18006ee38  mov     [rsp+98h+var_68], rax
0x18006ee3d  mov     [r15+rdi*8+40h], r13
0x18006ee42  mov     dword ptr [r15+rdi*8+48h], 0
0x18006ee4b  lea     rax, [rdx+rax*8]
0x18006ee4f  mov     [r15+rdi*8+50h], rax
0x18006ee54  mov     rcx, [rbp+rsi*8+0]; Sid
0x18006ee59  call    cs:__imp_RtlSubAuthorityCountSid
0x18006ee5f  dec     byte ptr [rax]
0x18006ee61  mov     rbx, [rbp+rsi*8+0]
0x18006ee66  mov     rdi, [r15+rdi*8+40h]
0x18006ee6b  mov     rcx, rbx; Sid
0x18006ee6e  call    cs:__imp_RtlLengthSid
0x18006ee74  mov     r8, rbx; SourceSid
0x18006ee77  mov     rdx, rdi; DestinationSid
0x18006ee7a  mov     ecx, eax; DestinationSidLength
0x18006ee7c  call    cs:__imp_RtlCopySid
0x18006ee82  mov     rcx, [rbp+rsi*8+0]; Sid
0x18006ee87  mov     ebx, eax
0x18006ee89  call    cs:__imp_RtlLengthSid
0x18006ee8f  mov     rcx, [rbp+rsi*8+0]; Sid
0x18006ee94  mov     edi, eax
0x18006ee96  call    cs:__imp_RtlSubAuthorityCountSid
0x18006ee9c  inc     byte ptr [rax]
0x18006ee9e  test    ebx, ebx
0x18006eea0  js      loc_18006EFCA
0x18006eea6  mov     ecx, [rsp+98h+var_78]
0x18006eeaa  add     r13, rdi
0x18006eead  mov     edi, [rsp+98h+arg_10]
0x18006eeb4  mov     rsi, [rsp+98h+var_60]
0x18006eeb9  mov     [rsp+98h+var_74], ecx
0x18006eebd  mov     eax, [rsp+98h+arg_0]
0x18006eec4  add     rsi, rsi
0x18006eec7  mov     rdx, [rsp+98h+var_70]
0x18006eecc  lea     rcx, [rax+rax*2]
0x18006eed0  inc     dword ptr [r15+rcx*8+48h]
0x18006eed5  mov     rcx, [rsp+98h+var_68]
0x18006eeda  mov     eax, [rbp+rsi*8+8]
0x18006eede  mov     [rdx+rcx*8+4], eax
0x18006eee2  mov     edx, 4; SubAuthority
  ... truncated ...
```
