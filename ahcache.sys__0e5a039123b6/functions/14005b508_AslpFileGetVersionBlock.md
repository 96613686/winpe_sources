# AslpFileGetVersionBlock

- ea: `0x14005b508`
- end: `0x14005bb70`
- name: `AslpFileGetVersionBlock`
- size: `1640`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x140025b04`

## callees

- `0x140004034`
- `0x140004445`
- `0x1400044f9`
- `0x1400045b0`
- `0x140006974`
- `0x140006c90`
- `0x140006cd8`
- `0x140006d5c`
- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x140045d44`
- `0x14004ae38`
- `0x14005498c`
- `0x14005b508`

## import_xrefs

- `ntoskrnl!LdrResSearchResource` at `0x14005b677`
- `ntoskrnl!LdrResSearchResource` at `0x14005b807`
- `ntoskrnl!LdrResSearchResource` at `0x14005b677`
- `ntoskrnl!LdrResSearchResource` at `0x14005b807`
- `ntoskrnl!VerSetConditionMask` at `0x14005b6fb`
- `ntoskrnl!VerSetConditionMask` at `0x14005b710`
- `ntoskrnl!VerSetConditionMask` at `0x14005b6fb`
- `ntoskrnl!VerSetConditionMask` at `0x14005b710`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14005b72a`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14005b72a`

## string_xrefs

- `0x14005b943`: `Version block has bad size (falls outside file)`
- `0x14005bac1`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlock(_QWORD *a1, __int64 *a2, __int64 a3)
{
  _WORD *v6; // r15
  __int64 v7; // rcx
  unsigned __int16 v8; // ax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  ULONGLONG v14; // rax
  ULONGLONG v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const wchar_t *v19; // rax
  const char *v20; // r9
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r11
  size_t v24; // rcx
  __int64 v25; // r11
  __int64 v27; // [rsp+20h] [rbp-228h]
  __int64 v28; // [rsp+20h] [rbp-228h]
  size_t Size; // [rsp+48h] [rbp-200h] BYREF
  void *Src; // [rsp+50h] [rbp-1F8h] BYREF
  _WORD *v31; // [rsp+58h] [rbp-1F0h]
  unsigned __int128 v32; // [rsp+60h] [rbp-1E8h] BYREF
  __int128 v33; // [rsp+70h] [rbp-1D8h] BYREF
  _QWORD *v34; // [rsp+80h] [rbp-1C8h]
  __int64 v35; // [rsp+88h] [rbp-1C0h]
  __int128 v36; // [rsp+90h] [rbp-1B8h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-1A8h]
  __int128 v38; // [rsp+B0h] [rbp-198h]
  __int64 v39; // [rsp+C0h] [rbp-188h]
  _OSVERSIONINFOEXW VersionInfo; // [rsp+D0h] [rbp-178h] BYREF
  _QWORD v41[3]; // [rsp+1F0h] [rbp-58h] BYREF

  v34 = a1;
  v35 = a3;
  Src = 0;
  v6 = 0;
  v31 = 0;
  Size = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v32 = 0;
  v33 = 0;
  v7 = *(_QWORD *)(a3 + 72);
  if ( !v7 )
  {
    v12 = AslFileMappingEnsure(a3);
    v11 = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1527, "AslFileMappingEnsure failed [%x]", v12);
      goto LABEL_56;
    }
    if ( *(_DWORD *)(a3 + 64) != 6 )
    {
      v11 = -1073741687;
      goto LABEL_56;
    }
    v41[0] = 16;
    v41[1] = 1;
    v41[2] = 0;
    AslpMemorySpanInitViewFromFileMapping(&v32, a3);
    v13 = LdrResSearchResource(*(_QWORD *)(a3 + 32), v41, 3, *(_BYTE *)(a3 + 59) == 0 ? 0x200 : 0, &Src, &Size, 0, 0);
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( (unsigned int)(v13 + 1073741687) <= 2 )
        goto LABEL_56;
      if ( v13 != -1073741701 || *(_BYTE *)(a3 + 59) || *(_DWORD *)(a3 + 84) )
      {
        AslLogCallPrintf(
          1,
          "AslpFileGetVersionBlock",
          1651,
          "LdrResFindResource failed %ls [%x]",
          *(const wchar_t **)a3,
          v13);
        goto LABEL_56;
      }
      memset(&VersionInfo, 0, sizeof(VersionInfo));
      VersionInfo.dwOSVersionInfoSize = 284;
      VersionInfo.dwMajorVersion = 6;
      VersionInfo.dwMinorVersion = 2;
      v14 = VerSetConditionMask(0, 2u, 3u);
      v15 = VerSetConditionMask(v14, 1u, 3u);
      if ( RtlVerifyVersionInfo(&VersionInfo, 3u, v15) < 0 )
      {
LABEL_15:
        v11 = -1073741687;
        goto LABEL_56;
      }
      v17 = *(_QWORD *)(a3 + 8);
      LOBYTE(v39) = 0;
      *(_QWORD *)&v36 = v17;
      LOBYTE(v16) = 1;
      v18 = RtlFileMapMapViewEx(&v36, v16, 0);
      v11 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v27) = v18;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1618, "RtlFileMapMapView failed [%x]", v27);
        goto LABEL_56;
      }
      AslLogCallPrintf(
        3,
        "AslpFileGetVersionBlock",
        1627,
        "Re-mapped file as image to get version block: %ls",
        *(const wchar_t **)a3);
      v11 = LdrResSearchResource(*((_QWORD *)&v37 + 1), v41, 3, 0, &Src, &Size, 0, 0);
      v19 = L"Found";
      if ( v11 < 0 )
        v19 = L"Did not find";
      AslLogCallPrintf(2, "AslpFileGetVersionBlock", 1640, "%ls version block after re-mapping as image [%x]", v19, v11);
      if ( v11 < 0 )
      {
        LODWORD(v28) = v11;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1643, "LdrResFindResource failed [%x]", v28);
        goto LABEL_56;
      }
      v32 = __PAIR128__(v38, *((unsigned __int64 *)&v37 + 1));
    }
    if ( !Src )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetVersionBlock",
        1658,
        "LdrResFindResource returned null version block with status: [%x]",
        v11);
      goto LABEL_15;
    }
    if ( Size < 0x26 )
    {
      v20 = "Version block is too small to be valid";
      v21 = 1665;
      goto LABEL_54;
    }
    if ( Size > 0x8000 )
    {
      v20 = "Version block is too large to be valid";
      v21 = 1675;
      goto LABEL_54;
    }
    *(_QWORD *)&v33 = Src;
    *((_QWORD *)&v33 + 1) = Size;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v33, &v32) )
    {
      v11 = -1073741687;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1686, "Version block has bad size (falls outside file)");
      goto LABEL_56;
    }
    v6 = (_WORD *)AslAlloc(v22, v23, 1);
    v31 = v6;
    if ( !v6 )
    {
      v11 = -1073741801;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1698, "Out of memory");
      goto LABEL_56;
    }
    if ( (unsigned __int8)MmIsUserAddress_0(Src) )
      RtlCopyFromUser(v6, Src, Size);
    else
      memmove(v6, Src, Size);
    if ( (unsigned int)Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( Size < 0x5C || wcsicmp_0((const wchar_t *)Src + 3, L"VS_VERSION_INFO") )
      {
        v21 = 1722;
LABEL_53:
        v20 = "Version block invalid";
LABEL_54:
        v11 = -1073741595;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", v21, v20);
        goto LABEL_56;
      }
    }
    else if ( Size < 0x26 || wcsicmp_0((const wchar_t *)Src + 3, L"VS_VERSION_INFO") )
    {
      v21 = 1729;
      goto LABEL_53;
    }
    v24 = (unsigned __int16)*v6;
    if ( (unsigned __int16)v24 < 0x5Cu )
    {
      v20 = "Version block invalid (too small to contain data)";
      v21 = 1743;
      goto LABEL_54;
    }
    if ( Size < v24 )
    {
      AslLogCallPrintf(
        3,
        "AslpFileGetVersionBlock",
        1752,
        "LdrResSearchResource returned a VersionBlockSize smaller than reflected in the actual block data.");
      *v6 = Size;
      LOWORD(v24) = Size;
    }
    *(_QWORD *)&v32 = v6;
    *((_QWORD *)&v32 + 1) = (unsigned __int16)v24;
    *(_QWORD *)&v33 = v6 + 20;
    *((_QWORD *)&v33 + 1) = 52;
    if ( (unsigned __int8)AslpMemorySpanCheckBounds(&v33, &v32) )
    {
      *a2 = v25;
    }
    else
    {
      *a2 = 0;
      if ( v6[1] )
      {
        v20 = "Version block invalid (fixed info falls outside root)";
        v21 = 1776;
        goto LABEL_54;
      }
    }
    *(_QWORD *)(a3 + 72) = v6;
    v6 = 0;
    v31 = 0;
    v9 = (__int64)v34;
    *v34 = *(_QWORD *)(a3 + 72);
    v11 = 0;
    goto LABEL_56;
  }
  v8 = *(_WORD *)(v7 + 2);
  v9 = v7 + 40;
  v10 = 0;
  if ( v8 >= 0x34u )
    v10 = v9;
  *a2 = v10;
  *a1 = *(_QWORD *)(a3 + 72);
  v11 = 0;
LABEL_56:
  if ( v6 )
    AslFree(v9, v6);
  RtlFileMapFree(&v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14005b508  push    rbx
0x14005b50a  push    rsi
0x14005b50b  push    rdi
0x14005b50c  push    r12
0x14005b50e  push    r13
0x14005b510  push    r14
0x14005b512  push    r15
0x14005b514  sub     rsp, 210h
0x14005b51b  mov     rax, cs:__security_cookie
0x14005b522  xor     rax, rsp
0x14005b525  mov     [rsp+248h+var_40], rax
0x14005b52d  mov     r12, r8
0x14005b530  mov     r13, rdx
0x14005b533  mov     r9, rcx
0x14005b536  mov     [rsp+248h+var_1C8], rcx
0x14005b53e  mov     [rsp+248h+var_1C0], r8
0x14005b546  xor     edi, edi
0x14005b548  mov     [rsp+248h+Src], rdi
0x14005b54d  mov     r15d, edi
0x14005b550  mov     [rsp+248h+var_1F0], rdi
0x14005b555  mov     [rsp+248h+Size], rdi
0x14005b55a  xorps   xmm0, xmm0
0x14005b55d  xor     eax, eax
0x14005b55f  movups  [rsp+248h+var_1B8], xmm0
0x14005b567  movups  [rsp+248h+var_1A8], xmm0
0x14005b56f  movups  [rsp+248h+var_198], xmm0
0x14005b577  mov     [rsp+248h+var_188], rax
0x14005b57f  movups  [rsp+248h+var_1E8], xmm0
0x14005b584  xorps   xmm1, xmm1
0x14005b587  movups  [rsp+248h+var_1D8], xmm1
0x14005b58c  mov     rcx, [r8+48h]
0x14005b590  test    rcx, rcx
0x14005b593  jz      short loc_14005B5BE
0x14005b595  movzx   eax, word ptr [rcx+2]
0x14005b599  add     rcx, 28h ; '('
0x14005b59d  mov     edx, edi
0x14005b59f  lea     r8d, [rdi+34h]
0x14005b5a3  cmp     ax, r8w
0x14005b5a7  cmovnb  rdx, rcx
0x14005b5ab  mov     [r13+0], rdx
0x14005b5af  mov     rax, [r12+48h]
0x14005b5b4  mov     [r9], rax
0x14005b5b7  mov     ebx, edi
0x14005b5b9  jmp     loc_14005BB30
0x14005b5be  mov     rcx, r12
0x14005b5c1  call    AslFileMappingEnsure
0x14005b5c6  mov     ebx, eax
0x14005b5c8  test    eax, eax
0x14005b5ca  jns     short loc_14005B5F3
0x14005b5cc  mov     dword ptr [rsp+248h+var_228], eax
0x14005b5d0  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14005b5d7  mov     r8d, 5F7h
0x14005b5dd  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14005b5e4  mov     ecx, 1
0x14005b5e9  call    AslLogCallPrintf
0x14005b5ee  jmp     loc_14005BB30
0x14005b5f3  cmp     dword ptr [r12+40h], 6
0x14005b5f9  jz      short loc_14005B605
0x14005b5fb  mov     ebx, 0C0000089h
0x14005b600  jmp     loc_14005BB30
0x14005b605  mov     [rsp+248h+var_58], 10h
0x14005b611  mov     r14d, 1
0x14005b617  mov     [rsp+248h+var_50], r14
0x14005b61f  mov     [rsp+248h+var_48], rdi
0x14005b627  mov     rdx, r12
0x14005b62a  lea     rcx, [rsp+248h+var_1E8]
0x14005b62f  call    AslpMemorySpanInitViewFromFileMapping
0x14005b634  mov     al, [r12+3Bh]
0x14005b639  neg     al
0x14005b63b  sbb     r9d, r9d
0x14005b63e  not     r9d
0x14005b641  and     r9d, 200h
0x14005b648  mov     [rsp+248h+var_210], rdi
0x14005b64d  mov     [rsp+248h+var_218], rdi
0x14005b652  lea     rax, [rsp+248h+Size]
0x14005b657  mov     [rsp+248h+var_220], rax
0x14005b65c  lea     rax, [rsp+248h+Src]
0x14005b661  mov     [rsp+248h+var_228], rax
0x14005b666  lea     r8d, [r14+2]
0x14005b66a  lea     rdx, [rsp+248h+var_58]
0x14005b672  mov     rcx, [r12+20h]
0x14005b677  call    cs:__imp_LdrResSearchResource
0x14005b67e  nop     dword ptr [rax+rax+00h]
0x14005b683  mov     ebx, eax
0x14005b685  mov     [rsp+248h+var_208], eax
0x14005b689  test    eax, eax
0x14005b68b  jns     loc_14005B8B7
0x14005b691  add     eax, 3FFFFF77h
0x14005b696  lea     esi, [r14+1]
0x14005b69a  cmp     eax, esi
0x14005b69c  jbe     loc_14005BAF1
0x14005b6a2  cmp     ebx, 0C000007Bh
0x14005b6a8  jnz     loc_14005B889
0x14005b6ae  cmp     [r12+3Bh], dil
0x14005b6b3  jnz     loc_14005B889
0x14005b6b9  cmp     [r12+54h], edi
0x14005b6be  jnz     loc_14005B889
0x14005b6c4  mov     ebx, 11Ch
0x14005b6c9  mov     r8d, ebx; Size
0x14005b6cc  xor     edx, edx; Val
0x14005b6ce  lea     rcx, [rsp+248h+VersionInfo]; void *
0x14005b6d6  call    memset
0x14005b6db  mov     [rsp+248h+VersionInfo.dwOSVersionInfoSize], ebx
0x14005b6e2  mov     [rsp+248h+VersionInfo.dwMajorVersion], 6
0x14005b6ed  mov     [rsp+248h+VersionInfo.dwMinorVersion], esi
0x14005b6f4  mov     r8b, 3; Condition
0x14005b6f7  mov     edx, esi; TypeMask
0x14005b6f9  xor     ecx, ecx; ConditionMask
0x14005b6fb  call    cs:__imp_VerSetConditionMask
0x14005b702  nop     dword ptr [rax+rax+00h]
0x14005b707  mov     r8b, 3; Condition
0x14005b70a  mov     edx, r14d; TypeMask
0x14005b70d  mov     rcx, rax; ConditionMask
0x14005b710  call    cs:__imp_VerSetConditionMask
0x14005b717  nop     dword ptr [rax+rax+00h]
0x14005b71c  mov     r8, rax; ConditionMask
0x14005b71f  lea     edx, [rsi+1]; TypeMask
0x14005b722  lea     rcx, [rsp+248h+VersionInfo]; VersionInfo
0x14005b72a  call    cs:__imp_RtlVerifyVersionInfo
0x14005b731  nop     dword ptr [rax+rax+00h]
0x14005b736  mov     [rsp+248h+var_208], eax
0x14005b73a  test    eax, eax
0x14005b73c  jns     short loc_14005B74C
0x14005b73e  mov     ebx, 0C0000089h
0x14005b743  mov     [rsp+248h+var_208], ebx
0x14005b747  jmp     loc_14005BAF1
0x14005b74c  mov     rax, [r12+8]
0x14005b751  mov     byte ptr [rsp+248h+var_188], dil
0x14005b759  mov     qword ptr [rsp+248h+var_1B8], rax
0x14005b761  mov     [rsp+248h+var_208], edi
0x14005b765  xor     r8d, r8d
0x14005b768  mov     dl, r14b
0x14005b76b  lea     rcx, [rsp+248h+var_1B8]
0x14005b773  call    RtlFileMapMapViewEx
0x14005b778  mov     ebx, eax
0x14005b77a  mov     [rsp+248h+var_208], eax
0x14005b77e  test    eax, eax
0x14005b780  jns     short loc_14005B7A7
0x14005b782  mov     dword ptr [rsp+248h+var_228], eax
0x14005b786  lea     r9, aRtlfilemapmapv; "RtlFileMapMapView failed [%x]"
0x14005b78d  mov     r8d, 652h
0x14005b793  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14005b79a  mov     ecx, r14d
0x14005b79d  call    AslLogCallPrintf
0x14005b7a2  jmp     loc_14005BAF1
0x14005b7a7  mov     rax, [r12]
0x14005b7ab  mov     [rsp+248h+var_228], rax
0x14005b7b0  lea     r9, aReMappedFileAs; "Re-mapped file as image to get version "...
0x14005b7b7  mov     r8d, 65Bh
0x14005b7bd  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14005b7c4  mov     rdx, rsi
0x14005b7c7  mov     ebx, 3
0x14005b7cc  mov     ecx, ebx
0x14005b7ce  call    AslLogCallPrintf
0x14005b7d3  mov     [rsp+248h+var_210], rdi
0x14005b7d8  mov     [rsp+248h+var_218], rdi
0x14005b7dd  lea     rax, [rsp+248h+Size]
0x14005b7e2  mov     [rsp+248h+var_220], rax
0x14005b7e7  lea     rax, [rsp+248h+Src]
0x14005b7ec  mov     [rsp+248h+var_228], rax
0x14005b7f1  xor     r9d, r9d
0x14005b7f4  mov     r8d, ebx
0x14005b7f7  lea     rdx, [rsp+248h+var_58]
0x14005b7ff  mov     rcx, qword ptr [rsp+248h+var_1A8+8]
0x14005b807  call    cs:__imp_LdrResSearchResource
0x14005b80e  nop     dword ptr [rax+rax+00h]
0x14005b813  mov     ebx, eax
0x14005b815  mov     [rsp+248h+var_208], eax
0x14005b819  lea     rax, aFound; "Found"
0x14005b820  lea     rdx, aDidNotFind; "Did not find"
0x14005b827  test    ebx, ebx
0x14005b829  cmovs   rax, rdx
0x14005b82d  mov     dword ptr [rsp+248h+var_220], ebx
0x14005b831  mov     [rsp+248h+var_228], rax
0x14005b836  lea     r9, aLsVersionBlock; "%ls version block after re-mapping as i"...
0x14005b83d  mov     r8d, 668h
0x14005b843  mov     rdx, rsi
0x14005b846  mov     ecx, 2
0x14005b84b  call    AslLogCallPrintf
0x14005b850  test    ebx, ebx
0x14005b852  jns     short loc_14005B86D
0x14005b854  mov     dword ptr [rsp+248h+var_228], ebx
0x14005b858  lea     r9, aLdrresfindreso_0; "LdrResFindResource failed [%x]"
0x14005b85f  mov     r8d, 66Bh
0x14005b865  mov     rdx, rsi
0x14005b868  jmp     loc_14005B79A
0x14005b86d  mov     rax, qword ptr [rsp+248h+var_1A8+8]
0x14005b875  mov     qword ptr [rsp+248h+var_1E8], rax
0x14005b87a  mov     rax, qword ptr [rsp+248h+var_198]
0x14005b882  mov     qword ptr [rsp+248h+var_1E8+8], rax
0x14005b887  jmp     short loc_14005B8BE
0x14005b889  mov     dword ptr [rsp+248h+var_220], ebx
0x14005b88d  mov     rax, [r12]
0x14005b891  mov     [rsp+248h+var_228], rax
0x14005b896  lea     r9, aLdrresfindreso; "LdrResFindResource failed %ls [%x]"
0x14005b89d  mov     r8d, 673h
0x14005b8a3  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14005b8aa  mov     ecx, r14d
0x14005b8ad  call    AslLogCallPrintf
0x14005b8b2  jmp     loc_14005BAF1
0x14005b8b7  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x14005b8be  mov     rax, [rsp+248h+Src]
0x14005b8c3  test    rax, rax
0x14005b8c6  jnz     short loc_14005B8E9
0x14005b8c8  mov     dword ptr [rsp+248h+var_228], ebx
0x14005b8cc  lea     r9, aLdrresfindreso_1; "LdrResFindResource returned null versio"...
0x14005b8d3  mov     r8d, 67Ah
0x14005b8d9  mov     rdx, rsi
0x14005b8dc  mov     ecx, r14d
0x14005b8df  call    AslLogCallPrintf
0x14005b8e4  jmp     loc_14005B73E
0x14005b8e9  mov     r11, [rsp+248h+Size]
0x14005b8ee  cmp     r11, 26h ; '&'
0x14005b8f2  jnb     short loc_14005B906
0x14005b8f4  lea     r9, aVersionBlockIs_0; "Version block is too small to be valid"
0x14005b8fb  mov     r8d, 681h
0x14005b901  jmp     loc_14005BADD
0x14005b906  cmp     r11, 8000h
0x14005b90d  jbe     short loc_14005B921
0x14005b90f  lea     r9, aVersionBlockIs; "Version block is too large to be valid"
0x14005b916  mov     r8d, 68Bh
0x14005b91c  jmp     loc_14005BADD
0x14005b921  mov     qword ptr [rsp+248h+var_1D8], rax
0x14005b926  mov     qword ptr [rsp+248h+var_1D8+8], r11
0x14005b92b  lea     rdx, [rsp+248h+var_1E8]
0x14005b930  lea     rcx, [rsp+248h+var_1D8]
0x14005b935  call    AslpMemorySpanCheckBounds
0x14005b93a  test    al, al
0x14005b93c  jnz     short loc_14005B955
0x14005b93e  mov     ebx, 0C0000089h
0x14005b943  lea     r9, aVersionBlockHa; "Version block has bad size (falls outsi"...
0x14005b94a  mov     r8d, 696h
0x14005b950  jmp     loc_14005BAE2
0x14005b955  mov     r8d, r14d
0x14005b958  mov     rdx, r11
0x14005b95b  call    AslAlloc
0x14005b960  mov     r15, rax
0x14005b963  mov     [rsp+248h+var_1F0], rax
0x14005b968  test    rax, rax
0x14005b96b  jnz     short loc_14005B984
0x14005b96d  mov     ebx, 0C0000017h
0x14005b972  lea     r9, aOutOfMemory; "Out of memory"
0x14005b979  mov     r8d, 6A2h
0x14005b97f  jmp     loc_14005BAE2
0x14005b984  mov     rcx, [rsp+248h+Src]
0x14005b989  call    MmIsUserAddress_0
0x14005b98e  mov     r8, [rsp+248h+Size]; Size
0x14005b993  mov     rdx, [rsp+248h+Src]; Src
0x14005b998  mov     rcx, r15; void *
0x14005b99b  test    al, al
0x14005b99d  jz      short loc_14005B9A6
0x14005b99f  call    RtlCopyFromUser
0x14005b9a4  jmp     short loc_14005B9AB
0x14005b9a6  call    memmove
0x14005b9ab  call    Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline
0x14005b9b0  test    eax, eax
0x14005b9b2  jz      short loc_14005B9E4
0x14005b9b4  mov     ebx, 5Ch ; '\'
0x14005b9b9  cmp     [rsp+248h+Size], rbx
0x14005b9be  jb      short loc_14005B9D9
0x14005b9c0  mov     rcx, [rsp+248h+Src]
0x14005b9c5  add     rcx, 6; Str1
0x14005b9c9  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x14005b9d0  call    _wcsicmp_0
0x14005b9d5  test    eax, eax
0x14005b9d7  jz      short loc_14005BA10
0x14005b9d9  mov     r8d, 6BAh
0x14005b9df  jmp     loc_14005BAD6
0x14005b9e4  cmp     [rsp+248h+Size], 26h ; '&'
0x14005b9ea  jb      loc_14005BAD0
0x14005b9f0  mov     rcx, [rsp+248h+Src]
0x14005b9f5  add     rcx, 6; Str1
0x14005b9f9  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x14005ba00  call    _wcsicmp_0
0x14005ba05  test    eax, eax
0x14005ba07  jnz     loc_14005BAD0
0x14005ba0d  lea     ebx, [rax+5Ch]
0x14005ba10  movzx   ecx, word ptr [r15]
0x14005ba14  cmp     bx, cx
0x14005ba17  jbe     short loc_14005BA2B
0x14005ba19  lea     r9, aVersionBlockIn_1; "Version block invalid (too small to con"...
0x14005ba20  mov     r8d, 6CFh
0x14005ba26  jmp     loc_14005BADD
0x14005ba2b  cmp     [rsp+248h+Size], rcx
0x14005ba30  jnb     short loc_14005BA5A
0x14005ba32  lea     r9, aLdrressearchre; "LdrResSearchResource returned a Version"...
0x14005ba39  mov     r8d, 6D8h
0x14005ba3f  mov     rdx, rsi
0x14005ba42  mov     ecx, 3
0x14005ba47  call    AslLogCallPrintf
0x14005ba4c  mov     rax, [rsp+248h+Size]
0x14005ba51  mov     [r15], ax
0x14005ba55  mov     rcx, [rsp+248h+Size]
0x14005ba5a  mov     qword ptr [rsp+248h+var_1E8], r15
0x14005ba5f  movzx   eax, cx
0x14005ba62  mov     qword ptr [rsp+248h+var_1E8+8], rax
0x14005ba67  lea     r11, [r15+28h]
0x14005ba6b  mov     qword ptr [rsp+248h+var_1D8], r11
0x14005ba70  mov     r8d, 34h ; '4'
0x14005ba76  mov     qword ptr [rsp+248h+var_1D8+8], r8
  ... truncated ...
```
