# AslpFileGetVersionBlock

- ea: `0x1800579c0`
- end: `0x1800580ee`
- name: `AslpFileGetVersionBlock`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800577cc`

## callees

- `0x180001cf0`
- `0x180002790`
- `0x180002874`
- `0x1800543c0`
- `0x1800553b8`
- `0x180055a2c`
- `0x1800579c0`
- `0x180059984`
- `0x180065150`

## import_xrefs

- `KERNEL32!VerSetConditionMask` at `0x180057bb2`
- `KERNEL32!VerSetConditionMask` at `0x180057bc1`
- `KERNEL32!VerSetConditionMask` at `0x180057bb2`
- `KERNEL32!VerSetConditionMask` at `0x180057bc1`
- `ntdll!RtlAllocateHeap` at `0x180057e2a`
- `ntdll!RtlAllocateHeap` at `0x180057e2a`
- `ntdll!RtlFreeHeap` at `0x180058068`
- `ntdll!RtlFreeHeap` at `0x180058068`
- `ntdll!ZwClose` at `0x180058085`
- `ntdll!ZwClose` at `0x1800580c3`
- `ntdll!ZwClose` at `0x180058085`
- `ntdll!ZwClose` at `0x1800580c3`
- `ntdll!ZwUnmapViewOfSection` at `0x1800580a6`
- `ntdll!ZwUnmapViewOfSection` at `0x1800580a6`
- `ntdll!LdrResSearchResource` at `0x180057b33`
- `ntdll!LdrResSearchResource` at `0x180057ca6`
- `ntdll!LdrResSearchResource` at `0x180057b33`
- `ntdll!LdrResSearchResource` at `0x180057ca6`
- `ntdll!RtlVerifyVersionInfo` at `0x180057bd4`
- `ntdll!RtlVerifyVersionInfo` at `0x180057bd4`

## string_xrefs

- `0x180057ff1`: `Version block has bad size (falls outside file)`
- `0x180057fc3`: `Version block invalid (fixed info falls outside root)`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlock(unsigned __int16 **a1, unsigned __int16 **a2, __int64 a3)
{
  unsigned __int16 *v5; // r12
  __int64 v6; // r8
  unsigned __int16 *v7; // rcx
  int v8; // ebx
  int v9; // eax
  char *v10; // rcx
  SIZE_T v11; // r12
  char *v12; // r13
  int v13; // eax
  ULONGLONG v14; // rax
  ULONGLONG v15; // rax
  void *v16; // rax
  int v17; // eax
  const wchar_t *v18; // rax
  char *v19; // rcx
  char *v20; // rdx
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v22; // rbx
  const char *v23; // r9
  __int64 v24; // r8
  unsigned __int16 v25; // ax
  unsigned __int64 v26; // r9
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  unsigned __int16 *v29; // r8
  __int64 v31; // [rsp+20h] [rbp-228h]
  __int64 v32; // [rsp+20h] [rbp-228h]
  SIZE_T Size; // [rsp+48h] [rbp-200h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-1F8h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-1E8h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-1E0h]
  SIZE_T v37; // [rsp+70h] [rbp-1D8h]
  unsigned __int16 **v38; // [rsp+78h] [rbp-1D0h]
  HANDLE Handle[2]; // [rsp+80h] [rbp-1C8h] BYREF
  PVOID BaseAddress[2]; // [rsp+90h] [rbp-1B8h]
  __int128 v41; // [rsp+A0h] [rbp-1A8h]
  unsigned __int16 **v42; // [rsp+B0h] [rbp-198h]
  __int64 v43; // [rsp+B8h] [rbp-190h]
  void *v44; // [rsp+C0h] [rbp-188h]
  SIZE_T v45; // [rsp+C8h] [rbp-180h]
  _OSVERSIONINFOEXW VersionInfo; // [rsp+D0h] [rbp-178h] BYREF
  _QWORD v47[3]; // [rsp+1F0h] [rbp-58h] BYREF

  v38 = a2;
  v42 = a1;
  v43 = a3;
  Src[0] = 0;
  v5 = 0;
  v35 = 0;
  Size = 0;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)BaseAddress = 0;
  v41 = 0;
  v6 = *(_QWORD *)(a3 + 64);
  if ( !v6 )
  {
    v9 = AslFileMappingEnsure(a3, a2, 0, a2);
    v8 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1527, "AslFileMappingEnsure failed [%x]", v9);
      goto LABEL_69;
    }
    if ( *(_DWORD *)(a3 + 56) != 6 )
    {
      v8 = -1073741687;
      goto LABEL_69;
    }
    v47[0] = 16;
    v47[1] = 1;
    v47[2] = 0;
    v10 = *(char **)(a3 + 32);
    if ( v10 )
    {
      v36 = *(unsigned __int16 **)(a3 + 32);
      v11 = *(_QWORD *)(a3 + 40);
      v37 = v11;
      v12 = v10;
    }
    else
    {
      v36 = 0;
      v11 = 0;
      v37 = 0;
      v12 = 0;
    }
    v13 = LdrResSearchResource(v10, v47, 3, *(_BYTE *)(a3 + 51) == 0 ? 0x200 : 0, Src, &Size, 0, 0);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( (unsigned int)(v13 + 1073741687) <= 2 )
      {
LABEL_68:
        v5 = 0;
        goto LABEL_69;
      }
      if ( v13 != -1073741701 || *(_BYTE *)(a3 + 51) || *(_DWORD *)(a3 + 76) )
      {
        AslLogCallPrintf(
          1,
          "AslpFileGetVersionBlock",
          1651,
          "LdrResFindResource failed %ls [%x]",
          *(const wchar_t **)a3,
          v13);
        goto LABEL_68;
      }
      memset_0(&VersionInfo, 0, sizeof(VersionInfo));
      VersionInfo.dwOSVersionInfoSize = 284;
      VersionInfo.dwMajorVersion = 6;
      VersionInfo.dwMinorVersion = 2;
      v14 = VerSetConditionMask(0, 2u, 3u);
      v15 = VerSetConditionMask(v14, 1u, 3u);
      if ( RtlVerifyVersionInfo(&VersionInfo, 3u, v15) < 0 )
      {
LABEL_18:
        v8 = -1073741687;
        goto LABEL_68;
      }
      v16 = *(void **)(a3 + 8);
      BYTE8(v41) = 0;
      Handle[0] = v16;
      v17 = RtlFileMapMapView((__int64)Handle, 1);
      v8 = v17;
      if ( v17 < 0 )
      {
        LODWORD(v31) = v17;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1618, "RtlFileMapMapView failed [%x]", v31);
        goto LABEL_68;
      }
      AslLogCallPrintf(
        3,
        "AslpFileGetVersionBlock",
        1627,
        "Re-mapped file as image to get version block: %ls",
        *(const wchar_t **)a3);
      v8 = LdrResSearchResource(BaseAddress[1], v47, 3, 0, Src, &Size, 0, 0);
      v18 = L"Found";
      if ( v8 < 0 )
        v18 = L"Did not find";
      AslLogCallPrintf(2, "AslpFileGetVersionBlock", 1640, "%ls version block after re-mapping as image [%x]", v18, v8);
      if ( v8 < 0 )
      {
        LODWORD(v32) = v8;
        AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1643, "LdrResFindResource failed [%x]", v32);
        goto LABEL_68;
      }
      v12 = (char *)BaseAddress[1];
      v36 = (unsigned __int16 *)BaseAddress[1];
      v11 = v41;
      v37 = v41;
    }
    if ( !Src[0] )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetVersionBlock",
        1658,
        "LdrResFindResource returned null version block with status: [%x]",
        v8);
      goto LABEL_18;
    }
    if ( Size < 0x26 )
    {
      v8 = -1073741595;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1665, "Version block is too small to be valid");
      goto LABEL_68;
    }
    if ( Size > 0x8000 )
    {
      v8 = -1073741595;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1675, "Version block is too large to be valid");
      goto LABEL_68;
    }
    v44 = Src[0];
    v45 = Size;
    if ( Src[0] < v12
      || (v19 = (char *)Src[0] + Size, Src[0] > (char *)Src[0] + Size)
      || (v20 = &v12[v11], Src[0] > &v12[v11])
      || v19 < v12
      || v19 > v20
      || v12 > v20
      || Size > v11 )
    {
      v8 = -1073741687;
      AslLogCallPrintf(1, "AslpFileGetVersionBlock", 1686, "Version block has bad size (falls outside file)");
      goto LABEL_68;
    }
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    v22 = Heap;
    v5 = Heap;
    v35 = Heap;
    if ( Heap )
    {
      memmove_0(Heap, Src[0], Size);
      if ( (unsigned int)Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( Size < 0x5C || wcsicmp((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
        {
          v8 = -1073741595;
          v23 = "Version block invalid";
          v24 = 1722;
          goto LABEL_42;
        }
      }
      else if ( Size < 0x26 || wcsicmp((const wchar_t *)Src[0] + 3, L"VS_VERSION_INFO") )
      {
        v8 = -1073741595;
        v23 = "Version block invalid";
        v24 = 1729;
        goto LABEL_42;
      }
      if ( *v22 >= 0x5Cu )
      {
        if ( Size >= *v22 )
        {
          v25 = *v22;
        }
        else
        {
          AslLogCallPrintf(
            3,
            "AslpFileGetVersionBlock",
            1752,
            "LdrResSearchResource returned a VersionBlockSize smaller than reflected in the actual block data.");
          *v22 = Size;
          v25 = Size;
        }
        v36 = v22;
        v26 = v25;
        v37 = v25;
        v27 = v22 + 20;
        v44 = v22 + 20;
        v45 = 52;
        if ( v22 + 20 < v22
          || (v28 = v22 + 46, v22 + 20 >= v22 + 46)
          || (v29 = (unsigned __int16 *)((char *)v22 + v26), v27 > (unsigned __int16 *)((char *)v22 + v26))
          || v28 < v22
          || v28 > v29
          || v22 > v29
          || v26 < 0x34 )
        {
          *v38 = 0;
          if ( v22[1] )
          {
            v8 = -1073741595;
            v23 = "Version block invalid (fixed info falls outside root)";
            v24 = 1776;
            goto LABEL_42;
          }
        }
        else
        {
          *v38 = v27;
        }
        *(_QWORD *)(a3 + 64) = v22;
        v35 = 0;
        *v42 = v22;
        v8 = 0;
        goto LABEL_68;
      }
      v8 = -1073741595;
      v23 = "Version block invalid (too small to contain data)";
      v24 = 1743;
    }
    else
    {
      v8 = -1073741801;
      v23 = "Out of memory";
      v24 = 1698;
    }
LABEL_42:
    AslLogCallPrintf(1, "AslpFileGetVersionBlock", v24, v23);
    goto LABEL_69;
  }
  v7 = 0;
  if ( *(_WORD *)(v6 + 2) >= 0x34u )
    v7 = (unsigned __int16 *)(v6 + 40);
  *a2 = v7;
  *a1 = *(unsigned __int16 **)(a3 + 64);
  v8 = 0;
LABEL_69:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( BYTE8(v41) && Handle[0] )
    ZwClose(Handle[0]);
  if ( BYTE10(v41) && BaseAddress[1] )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress[1]);
  if ( BYTE9(v41) && Handle[1] )
    ZwClose(Handle[1]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800579c0  push    rbx
0x1800579c2  push    rsi
0x1800579c3  push    rdi
0x1800579c4  push    r12
0x1800579c6  push    r13
0x1800579c8  push    r14
0x1800579ca  push    r15
0x1800579cc  sub     rsp, 210h
0x1800579d3  mov     rax, cs:__security_cookie
0x1800579da  xor     rax, rsp
0x1800579dd  mov     [rsp+248h+var_40], rax
0x1800579e5  mov     r15, r8
0x1800579e8  mov     r9, rdx
0x1800579eb  mov     [rsp+248h+var_1D0], rdx
0x1800579f0  mov     r10, rcx
0x1800579f3  mov     [rsp+248h+var_198], rcx
0x1800579fb  mov     [rsp+248h+var_190], r8
0x180057a03  xor     edi, edi
0x180057a05  mov     [rsp+248h+Src], rdi
0x180057a0a  mov     r12d, edi
0x180057a0d  mov     [rsp+248h+var_1E8], rdi
0x180057a12  mov     [rsp+248h+Size], rdi
0x180057a17  xorps   xmm0, xmm0
0x180057a1a  movups  xmmword ptr [rsp+248h+Handle], xmm0
0x180057a22  movups  xmmword ptr [rsp+248h+BaseAddress], xmm0
0x180057a2a  movups  [rsp+248h+var_1A8], xmm0
0x180057a32  mov     r8, [r8+40h]
0x180057a36  test    r8, r8
0x180057a39  jz      short loc_180057A5E
0x180057a3b  lea     rax, [r8+28h]
0x180057a3f  mov     ecx, edi
0x180057a41  lea     edx, [rdi+34h]
0x180057a44  cmp     [r8+2], dx
0x180057a49  cmovnb  rcx, rax
0x180057a4d  mov     [r9], rcx
0x180057a50  mov     rax, [r15+40h]
0x180057a54  mov     [r10], rax
0x180057a57  mov     ebx, edi
0x180057a59  jmp     loc_180058051
0x180057a5e  mov     rcx, r15
0x180057a61  call    AslFileMappingEnsure
0x180057a66  mov     ebx, eax
0x180057a68  test    eax, eax
0x180057a6a  jns     short loc_180057A93
0x180057a6c  mov     dword ptr [rsp+248h+var_228], eax
0x180057a70  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x180057a77  mov     r8d, 5F7h
0x180057a7d  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180057a84  mov     ecx, 1
0x180057a89  call    AslLogCallPrintf
0x180057a8e  jmp     loc_180058051
0x180057a93  cmp     dword ptr [r15+38h], 6
0x180057a98  jz      short loc_180057AA4
0x180057a9a  mov     ebx, 0C0000089h
0x180057a9f  jmp     loc_180058051
0x180057aa4  mov     [rsp+248h+var_58], 10h
0x180057ab0  mov     r14d, 1
0x180057ab6  mov     [rsp+248h+var_50], r14
0x180057abe  mov     [rsp+248h+var_48], rdi
0x180057ac6  mov     rcx, [r15+20h]
0x180057aca  test    rcx, rcx
0x180057acd  jz      short loc_180057AE2
0x180057acf  mov     [rsp+248h+var_1E0], rcx
0x180057ad4  mov     r12, [r15+28h]
0x180057ad8  mov     [rsp+248h+var_1D8], r12
0x180057add  mov     r13, rcx
0x180057ae0  jmp     short loc_180057AF2
0x180057ae2  mov     [rsp+248h+var_1E0], rdi
0x180057ae7  mov     r12, rdi
0x180057aea  mov     [rsp+248h+var_1D8], rdi
0x180057aef  mov     r13, rdi
0x180057af2  mov     al, [r15+33h]
0x180057af6  neg     al
0x180057af8  sbb     r9d, r9d
0x180057afb  not     r9d
0x180057afe  and     r9d, 200h
0x180057b05  mov     [rsp+248h+var_210], rdi
0x180057b0a  mov     [rsp+248h+var_218], rdi
0x180057b0f  lea     rax, [rsp+248h+Size]
0x180057b14  mov     [rsp+248h+var_220], rax
0x180057b19  lea     rax, [rsp+248h+Src]
0x180057b1e  mov     [rsp+248h+var_228], rax
0x180057b23  mov     esi, 3
0x180057b28  mov     r8d, esi
0x180057b2b  lea     rdx, [rsp+248h+var_58]
0x180057b33  call    cs:__imp_LdrResSearchResource
0x180057b39  mov     ebx, eax
0x180057b3b  mov     [rsp+248h+var_208], eax
0x180057b3f  test    eax, eax
0x180057b41  jns     loc_180057D4D
0x180057b47  add     eax, 3FFFFF77h
0x180057b4c  lea     r12d, [rsi-1]
0x180057b50  cmp     eax, r12d
0x180057b53  jbe     loc_18005800D
0x180057b59  cmp     ebx, 0C000007Bh
0x180057b5f  jnz     loc_180057D20
0x180057b65  cmp     [r15+33h], dil
0x180057b69  jnz     loc_180057D20
0x180057b6f  cmp     [r15+4Ch], edi
0x180057b73  jnz     loc_180057D20
0x180057b79  mov     ebx, 11Ch
0x180057b7e  mov     r8d, ebx; Size
0x180057b81  xor     edx, edx; Val
0x180057b83  lea     rcx, [rsp+248h+VersionInfo]; void *
0x180057b8b  call    memset_0
0x180057b90  mov     [rsp+248h+VersionInfo.dwOSVersionInfoSize], ebx
0x180057b97  mov     [rsp+248h+VersionInfo.dwMajorVersion], 6
0x180057ba2  mov     [rsp+248h+VersionInfo.dwMinorVersion], r12d
0x180057baa  mov     r8b, sil; Condition
0x180057bad  mov     edx, r12d; TypeMask
0x180057bb0  xor     ecx, ecx; ConditionMask
0x180057bb2  call    cs:__imp_VerSetConditionMask
0x180057bb8  mov     r8b, sil; Condition
0x180057bbb  mov     edx, r14d; TypeMask
0x180057bbe  mov     rcx, rax; ConditionMask
0x180057bc1  call    cs:__imp_VerSetConditionMask
0x180057bc7  mov     r8, rax; ConditionMask
0x180057bca  mov     edx, esi; TypeMask
0x180057bcc  lea     rcx, [rsp+248h+VersionInfo]; VersionInfo
0x180057bd4  call    cs:__imp_RtlVerifyVersionInfo
0x180057bda  mov     [rsp+248h+var_208], eax
0x180057bde  test    eax, eax
0x180057be0  jns     short loc_180057BF0
0x180057be2  mov     ebx, 0C0000089h
0x180057be7  mov     [rsp+248h+var_208], ebx
0x180057beb  jmp     loc_18005800D
0x180057bf0  mov     rax, [r15+8]
0x180057bf4  mov     byte ptr [rsp+248h+var_1A8+8], dil
0x180057bfc  mov     [rsp+248h+Handle], rax
0x180057c04  mov     [rsp+248h+var_208], edi
0x180057c08  mov     dl, r14b
0x180057c0b  lea     rcx, [rsp+248h+Handle]
0x180057c13  call    RtlFileMapMapView
0x180057c18  mov     ebx, eax
0x180057c1a  mov     [rsp+248h+var_208], eax
0x180057c1e  test    eax, eax
0x180057c20  jns     short loc_180057C47
0x180057c22  mov     dword ptr [rsp+248h+var_228], eax
0x180057c26  lea     r9, aRtlfilemapmapv; "RtlFileMapMapView failed [%x]"
0x180057c2d  mov     r8d, 652h
0x180057c33  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180057c3a  mov     ecx, r14d
0x180057c3d  call    AslLogCallPrintf
0x180057c42  jmp     loc_18005800D
0x180057c47  mov     rax, [r15]
0x180057c4a  mov     [rsp+248h+var_228], rax
0x180057c4f  lea     r9, aReMappedFileAs; "Re-mapped file as image to get version "...
0x180057c56  mov     r8d, 65Bh
0x180057c5c  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180057c63  mov     rdx, rsi
0x180057c66  mov     ebx, 3
0x180057c6b  mov     ecx, ebx
0x180057c6d  call    AslLogCallPrintf
0x180057c72  mov     [rsp+248h+var_210], rdi
0x180057c77  mov     [rsp+248h+var_218], rdi
0x180057c7c  lea     rax, [rsp+248h+Size]
0x180057c81  mov     [rsp+248h+var_220], rax
0x180057c86  lea     rax, [rsp+248h+Src]
0x180057c8b  mov     [rsp+248h+var_228], rax
0x180057c90  xor     r9d, r9d
0x180057c93  mov     r8d, ebx
0x180057c96  lea     rdx, [rsp+248h+var_58]
0x180057c9e  mov     rcx, [rsp+248h+BaseAddress+8]
0x180057ca6  call    cs:__imp_LdrResSearchResource
0x180057cac  mov     ebx, eax
0x180057cae  mov     [rsp+248h+var_208], eax
0x180057cb2  lea     rax, aFound; "Found"
0x180057cb9  lea     rdx, aDidNotFind; "Did not find"
0x180057cc0  test    ebx, ebx
0x180057cc2  cmovs   rax, rdx
0x180057cc6  mov     dword ptr [rsp+248h+var_220], ebx
0x180057cca  mov     [rsp+248h+var_228], rax
0x180057ccf  lea     r9, aLsVersionBlock; "%ls version block after re-mapping as i"...
0x180057cd6  mov     r8d, 668h
0x180057cdc  mov     rdx, rsi
0x180057cdf  mov     ecx, r12d
0x180057ce2  call    AslLogCallPrintf
0x180057ce7  test    ebx, ebx
0x180057ce9  jns     short loc_180057D04
0x180057ceb  mov     dword ptr [rsp+248h+var_228], ebx
0x180057cef  lea     r9, aLdrresfindreso_0; "LdrResFindResource failed [%x]"
0x180057cf6  mov     r8d, 66Bh
0x180057cfc  mov     rdx, rsi
0x180057cff  jmp     loc_180057C3A
0x180057d04  mov     r13, [rsp+248h+BaseAddress+8]
0x180057d0c  mov     [rsp+248h+var_1E0], r13
0x180057d11  mov     r12, qword ptr [rsp+248h+var_1A8]
0x180057d19  mov     [rsp+248h+var_1D8], r12
0x180057d1e  jmp     short loc_180057D54
0x180057d20  mov     dword ptr [rsp+248h+var_220], ebx
0x180057d24  mov     rax, [r15]
0x180057d27  mov     [rsp+248h+var_228], rax
0x180057d2c  lea     r9, aLdrresfindreso; "LdrResFindResource failed %ls [%x]"
0x180057d33  mov     r8d, 673h
0x180057d39  lea     rdx, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180057d40  mov     ecx, r14d
0x180057d43  call    AslLogCallPrintf
0x180057d48  jmp     loc_18005800D
0x180057d4d  lea     rsi, aAslpfilegetver_4; "AslpFileGetVersionBlock"
0x180057d54  mov     rax, [rsp+248h+Src]
0x180057d59  test    rax, rax
0x180057d5c  jnz     short loc_180057D7F
0x180057d5e  mov     dword ptr [rsp+248h+var_228], ebx
0x180057d62  lea     r9, aLdrresfindreso_1; "LdrResFindResource returned null versio"...
0x180057d69  mov     r8d, 67Ah
0x180057d6f  mov     rdx, rsi
0x180057d72  mov     ecx, r14d
0x180057d75  call    AslLogCallPrintf
0x180057d7a  jmp     loc_180057BE2
0x180057d7f  mov     r8, [rsp+248h+Size]; Size
0x180057d84  cmp     r8, 26h ; '&'
0x180057d88  jnb     short loc_180057DA1
0x180057d8a  mov     ebx, 0C00000E5h
0x180057d8f  lea     r9, aVersionBlockIs_0; "Version block is too small to be valid"
0x180057d96  mov     r8d, 681h
0x180057d9c  jmp     loc_180057FFE
0x180057da1  cmp     r8, 8000h
0x180057da8  jbe     short loc_180057DC1
0x180057daa  mov     ebx, 0C00000E5h
0x180057daf  lea     r9, aVersionBlockIs; "Version block is too large to be valid"
0x180057db6  mov     r8d, 68Bh
0x180057dbc  jmp     loc_180057FFE
0x180057dc1  mov     [rsp+248h+var_188], rax
0x180057dc9  mov     [rsp+248h+var_180], r8
0x180057dd1  cmp     rax, r13
0x180057dd4  jb      loc_180057FEC
0x180057dda  lea     rcx, [r8+rax]
0x180057dde  cmp     rax, rcx
0x180057de1  ja      loc_180057FEC
0x180057de7  lea     rdx, [r12+r13]
0x180057deb  cmp     rax, rdx
0x180057dee  ja      loc_180057FEC
0x180057df4  cmp     rcx, r13
0x180057df7  jb      loc_180057FEC
0x180057dfd  cmp     rcx, rdx
0x180057e00  ja      loc_180057FEC
0x180057e06  cmp     r13, rdx
0x180057e09  ja      loc_180057FEC
0x180057e0f  cmp     r8, r12
0x180057e12  ja      loc_180057FEC
0x180057e18  mov     rcx, gs:60h
0x180057e21  mov     edx, 8; Flags
0x180057e26  mov     rcx, [rcx+30h]; HeapHandle
0x180057e2a  call    cs:__imp_RtlAllocateHeap
0x180057e30  mov     rbx, rax
0x180057e33  mov     r12, rax
0x180057e36  mov     [rsp+248h+var_1E8], rax
0x180057e3b  test    rax, rax
0x180057e3e  jnz     short loc_180057E66
0x180057e40  mov     ebx, 0C0000017h
0x180057e45  lea     r9, aOutOfMemory; "Out of memory"
0x180057e4c  mov     r8d, 6A2h
0x180057e52  mov     [rsp+248h+var_208], ebx
0x180057e56  mov     rdx, rsi
0x180057e59  mov     ecx, r14d
0x180057e5c  call    AslLogCallPrintf
0x180057e61  jmp     loc_180058010
0x180057e66  mov     r8, [rsp+248h+Size]; Size
0x180057e6b  mov     rdx, [rsp+248h+Src]; Src
0x180057e70  mov     rcx, rbx; void *
0x180057e73  call    memmove_0
0x180057e78  call    Feature_EnsureVerBlockCanHoldFixedInfo__private_IsEnabledDeviceUsageNoInline
0x180057e7d  test    eax, eax
0x180057e7f  jz      short loc_180057EBB
0x180057e81  mov     r13d, 5Ch ; '\'
0x180057e87  cmp     [rsp+248h+Size], r13
0x180057e8c  jb      short loc_180057EA7
0x180057e8e  mov     rcx, [rsp+248h+Src]
0x180057e93  add     rcx, 6; String1
0x180057e97  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x180057e9e  call    _wcsicmp
0x180057ea3  test    eax, eax
0x180057ea5  jz      short loc_180057EE8
0x180057ea7  mov     ebx, 0C00000E5h
0x180057eac  lea     r9, aVersionBlockIn_0; "Version block invalid"
0x180057eb3  mov     r8d, 6BAh
0x180057eb9  jmp     short loc_180057E52
0x180057ebb  cmp     [rsp+248h+Size], 26h ; '&'
0x180057ec1  jb      loc_180057FD5
0x180057ec7  mov     rcx, [rsp+248h+Src]
0x180057ecc  add     rcx, 6; String1
0x180057ed0  lea     rdx, aVsVersionInfo; "VS_VERSION_INFO"
0x180057ed7  call    _wcsicmp
0x180057edc  test    eax, eax
0x180057ede  jnz     loc_180057FD5
0x180057ee4  lea     r13d, [rax+5Ch]
0x180057ee8  cmp     r13w, [rbx]
0x180057eec  jbe     short loc_180057F05
0x180057eee  mov     ebx, 0C00000E5h
0x180057ef3  lea     r9, aVersionBlockIn_1; "Version block invalid (too small to con"...
0x180057efa  mov     r8d, 6CFh
0x180057f00  jmp     loc_180057E52
0x180057f05  movzx   eax, word ptr [rbx]
0x180057f08  cmp     [rsp+248h+Size], rax
0x180057f0d  jnb     short loc_180057F38
0x180057f0f  lea     r9, aLdrressearchre; "LdrResSearchResource returned a Version"...
0x180057f16  mov     r8d, 6D8h
0x180057f1c  mov     rdx, rsi
0x180057f1f  mov     ecx, 3
0x180057f24  call    AslLogCallPrintf
  ... truncated ...
```
