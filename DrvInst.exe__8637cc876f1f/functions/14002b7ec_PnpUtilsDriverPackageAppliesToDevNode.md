# PnpUtilsDriverPackageAppliesToDevNode

- ea: `0x14002b7ec`
- end: `0x14002bd3e`
- name: `PnpUtilsDriverPackageAppliesToDevNode`
- size: `1362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140011a78`
- `0x14001bd7c`
- `0x140022330`
- `0x14002a8e0`
- `0x14002bff4`

## callees

- `0x140001b64`
- `0x1400247dc`
- `0x140026424`
- `0x140026e58`
- `0x14002b7ec`
- `0x140045ec6`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ba98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ba98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bb09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bb8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bc58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bcca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bcf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bb09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bb8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bc58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bcca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002bcf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002bd13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002bd13`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002ba53`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002bae3`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002ba53`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002bae3`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002bc94`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002bc94`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002bb2b`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002bc71`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002bb2b`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14002bc71`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002b8c1`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002b97c`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002b8c1`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x14002b97c`
- `drvstore!DriverStoreFindW` at `0x14002b926`
- `drvstore!DriverStoreFindW` at `0x14002b926`
- `drvstore!DriverStoreOpenW` at `0x14002b874`
- `drvstore!DriverStoreOpenW` at `0x14002b874`
- `drvstore!DriverStoreClose` at `0x14002bd0b`
- `drvstore!DriverStoreClose` at `0x14002bd0b`

## pseudocode

```c
__int64 __fastcall PnpUtilsDriverPackageAppliesToDevNode(__int64 a1, unsigned int a2, BYTE *a3, wchar_t *a4)
{
  unsigned int v4; // r13d
  BYTE *v6; // rsi
  unsigned int v7; // r15d
  __int64 v8; // r14
  BYTE *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r12
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  CONFIGRET DevNode_PropertyW; // esi
  int v16; // r9d
  BYTE *v17; // rax
  ULONG v18; // ecx
  __int64 ThreadLogToken; // rax
  const char *v20; // r9
  BYTE *v21; // r14
  BYTE *v22; // r15
  const wchar_t *v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rax
  PULONG PropertyBufferSize; // [rsp+20h] [rbp-E0h]
  ULONG ulFlags[2]; // [rsp+28h] [rbp-D8h]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  ULONG *v30; // [rsp+38h] [rbp-C8h]
  __int64 v31; // [rsp+40h] [rbp-C0h]
  ULONG v32; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  unsigned int v36; // [rsp+68h] [rbp-98h]
  unsigned int v37; // [rsp+6Ch] [rbp-94h]
  wchar_t *String2; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+78h] [rbp-88h]
  wchar_t *v40; // [rsp+88h] [rbp-78h]
  __int128 Buf1; // [rsp+90h] [rbp-70h] BYREF
  BYTE v42[528]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE PropertyBuffer[2044]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v44; // [rsp+AACh] [rbp+9ACh]

  v4 = 0;
  v36 = a2;
  v35 = a1;
  PropertyType = 0;
  v32 = 0;
  lpMem = 0;
  v6 = a3;
  v40 = 0;
  v7 = a2;
  v8 = a1;
  v9 = 0;
  Buf1 = 0;
  v39 = 0;
  if ( !a3 && !a4 )
  {
    v10 = 0;
    goto LABEL_72;
  }
  if ( a1 )
    v11 = a1;
  else
    v11 = DriverStoreOpenW(0, 0, 0, 0);
  if ( !a4 )
  {
    DriverStoreGetObjectPropertyW(v11, 2, v6, DEVPKEY_DriverPackage_DriverInfName);
    LODWORD(v9) = 13;
    v10 = 0;
    goto LABEL_69;
  }
  String2 = a4;
  if ( !v6 )
  {
    if ( !(unsigned int)DriverStoreFindW(v11, a4, 0xFFFF, 0, 1, v42, 260, 0) )
    {
      LODWORD(v9) = 1;
      v10 = 0;
      goto LABEL_68;
    }
    v6 = v42;
  }
  LODWORD(v31) = 0;
  v30 = &v32;
  LODWORD(v29) = 16;
  if ( !(unsigned int)DriverStoreGetObjectPropertyW(v11, 2, v6, DEVPKEY_DriverPackage_ClassGuid)
    || v32 != 16
    || PropertyType != 13 )
  {
    LODWORD(v9) = 11;
    v10 = 0;
    goto LABEL_66;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&v39 = v11;
    DWORD2(v39) = 0;
    v40 = a4;
    memcmp_0(&Buf1, &GUID_DEVCLASS_EXTENSION, 0x10u);
    DevUtilsDeviceEnumDeviceIds(v7);
    v10 = DWORD2(v39);
    goto LABEL_68;
  }
  v10 = 0;
  v12 = memcmp_0(&Buf1, &GUID_DEVCLASS_EXTENSION, 0x10u);
  v13 = 2;
  if ( !v12 )
    v13 = 3;
  v37 = v13;
  while ( 1 )
  {
    memset_0(PropertyBuffer, 0, 0x800u);
    v32 = 2048;
    DevNode_PropertyW = CM_Get_DevNode_PropertyW(v7, off_140048970[v4], &PropertyType, PropertyBuffer, &v32, 0);
    if ( DevNode_PropertyW != 26 )
      break;
    if ( v4 < 2 )
      goto LABEL_60;
    if ( v32 <= 0x800 )
      goto LABEL_60;
    if ( PropertyType != 8210 )
      goto LABEL_60;
    v17 = (BYTE *)HeapAlloc(hHeap, 0, v32 + 4);
    v9 = v17;
    if ( !v17 )
      goto LABEL_60;
    memset_0(v17, 0, v32 + 4LL);
    if ( !CM_Get_DevNode_PropertyW(v7, off_140048970[v4], &PropertyType, v9, &v32, 0) && PropertyType == 8210 )
    {
      v18 = v32;
      goto LABEL_34;
    }
    HeapFree(hHeap, 0, v9);
    v9 = 0;
LABEL_60:
    if ( ++v4 >= v37 )
      goto LABEL_61;
  }
  if ( DevNode_PropertyW )
  {
    if ( DevNode_PropertyW == 37 )
      goto LABEL_60;
    ThreadLogToken = DevRtlGetThreadLogToken();
    v20 = "Unable to get device property index %d. cr = 0x%02x";
LABEL_59:
    ulFlags[0] = DevNode_PropertyW;
    LODWORD(PropertyBufferSize) = v4;
    DevRtlWriteTextLog(ThreadLogToken, 1, 2, v20, PropertyBufferSize, *(_QWORD *)ulFlags, v29, v30, v31);
    goto LABEL_60;
  }
  DevNode_PropertyW = PropertyType;
  if ( PropertyType != 8210 )
  {
    ThreadLogToken = DevRtlGetThreadLogToken();
    v20 = "Device property index %d is of unexpected type %d";
    goto LABEL_59;
  }
  v18 = 2048;
  v9 = PropertyBuffer;
  v32 = 2048;
  v44 = 0;
LABEL_34:
  v21 = v9;
  v22 = &v9[v18 & 0xFFFFFFFE];
  if ( v9 < v22 )
  {
    while ( *(_WORD *)v21 )
    {
      if ( lpMem )
      {
        HeapFree(hHeap, 0, lpMem);
        lpMem = 0;
      }
      if ( (unsigned int)DrvUtilsAllocDriverStoreProperty(
                           v11,
                           v14,
                           (_DWORD)v21,
                           v16,
                           (__int64)&PropertyType,
                           (__int64)&lpMem,
                           (__int64)&v32)
        && v32 >= 2
        && PropertyType == 8210 )
      {
        v23 = (const wchar_t *)lpMem;
        if ( *(_WORD *)lpMem )
        {
          while ( wcsicmp_0(v23, String2) )
          {
            v24 = -1;
            do
              ++v24;
            while ( v23[v24] );
            v23 += v24 + 1;
            if ( !*v23 )
              goto LABEL_46;
          }
          v10 = 1;
          break;
        }
      }
      else
      {
        v10 = 0;
      }
LABEL_46:
      v25 = -1;
      do
        ++v25;
      while ( *(_WORD *)&v21[2 * v25] );
      v21 += 2 * v25 + 2;
      if ( v21 >= v22 )
        break;
    }
  }
  if ( v9 && v9 != PropertyBuffer )
  {
    HeapFree(hHeap, 0, v9);
    v9 = 0;
  }
  if ( !v10 )
  {
    v7 = v36;
    goto LABEL_60;
  }
LABEL_61:
  if ( v9 && v9 != PropertyBuffer )
    HeapFree(hHeap, 0, v9);
  LODWORD(v9) = 0;
LABEL_66:
  if ( lpMem )
    HeapFree(hHeap, 0, lpMem);
LABEL_68:
  v8 = v35;
LABEL_69:
  if ( v11 && !v8 )
    DriverStoreClose(v11);
LABEL_72:
  SetLastError((DWORD)v9);
  return v10;
}

```

## disassembly

```asm
0x14002b7ec  push    rbp
0x14002b7ee  push    rbx
0x14002b7ef  push    rsi
0x14002b7f0  push    rdi
0x14002b7f1  push    r12
0x14002b7f3  push    r13
0x14002b7f5  push    r14
0x14002b7f7  push    r15
0x14002b7f9  lea     rbp, [rsp-9C8h]
0x14002b801  sub     rsp, 0AC8h
0x14002b808  mov     rax, cs:__security_cookie
0x14002b80f  xor     rax, rsp
0x14002b812  mov     [rbp+0A00h+var_50], rax
0x14002b819  xor     r13d, r13d
0x14002b81c  mov     [rsp+0B00h+var_A98], edx
0x14002b820  xor     eax, eax
0x14002b822  mov     [rsp+0B00h+var_AA0], rcx
0x14002b827  mov     [rsp+0B00h+PropertyType], r13d
0x14002b82c  xorps   xmm0, xmm0
0x14002b82f  mov     [rsp+0B00h+var_AB0], r13d
0x14002b834  mov     rbx, r9
0x14002b837  mov     [rsp+0B00h+lpMem], r13
0x14002b83c  mov     rsi, r8
0x14002b83f  mov     [rbp+0A00h+var_A78], rax
0x14002b843  mov     r15d, edx
0x14002b846  mov     r14, rcx
0x14002b849  mov     edi, r13d
0x14002b84c  movups  [rbp+0A00h+Buf1], xmm0
0x14002b850  movups  [rsp+0B00h+var_A88], xmm0
0x14002b855  test    r8, r8
0x14002b858  jnz     short loc_14002B867
0x14002b85a  test    rbx, rbx
0x14002b85d  jnz     short loc_14002B867
0x14002b85f  mov     ebx, r13d
0x14002b862  jmp     loc_14002BD11
0x14002b867  test    rcx, rcx
0x14002b86a  jnz     short loc_14002B87F
0x14002b86c  xor     r9d, r9d
0x14002b86f  xor     r8d, r8d
0x14002b872  xor     edx, edx
0x14002b874  call    cs:__imp_DriverStoreOpenW
0x14002b87a  mov     r12, rax
0x14002b87d  jmp     short loc_14002B882
0x14002b87f  mov     r12, rcx
0x14002b882  test    rbx, rbx
0x14002b885  jnz     short loc_14002B8EC
0x14002b887  mov     [rsp+0B00h+var_AC0], r13d
0x14002b88c  lea     rax, [rsp+0B00h+var_AB0]
0x14002b891  mov     [rsp+0B00h+var_AC8], rax
0x14002b896  lea     r9, DEVPKEY_DriverPackage_DriverInfName
0x14002b89d  lea     rax, [rbp+0A00h+var_A60]
0x14002b8a1  mov     dword ptr [rsp+0B00h+var_AD0], 208h
0x14002b8a9  mov     qword ptr [rsp+0B00h+ulFlags], rax
0x14002b8ae  lea     edx, [rbx+2]
0x14002b8b1  lea     rax, [rsp+0B00h+PropertyType]
0x14002b8b6  mov     r8, rsi
0x14002b8b9  mov     rcx, r12
0x14002b8bc  mov     [rsp+0B00h+PropertyBufferSize], rax
0x14002b8c1  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002b8c7  test    eax, eax
0x14002b8c9  jz      short loc_14002B8DF
0x14002b8cb  cmp     [rsp+0B00h+var_AB0], 2
0x14002b8d0  jb      short loc_14002B8DF
0x14002b8d2  cmp     [rsp+0B00h+PropertyType], 12h
0x14002b8d7  jnz     short loc_14002B8DF
0x14002b8d9  lea     r14, [rbp+0A00h+var_A60]
0x14002b8dd  jmp     short loc_14002B8EF
0x14002b8df  mov     edi, 0Dh
0x14002b8e4  mov     ebx, r13d
0x14002b8e7  jmp     loc_14002BCFE
0x14002b8ec  mov     r14, rbx
0x14002b8ef  mov     [rsp+0B00h+String2], r14
0x14002b8f4  test    rsi, rsi
0x14002b8f7  jnz     short loc_14002B93F
0x14002b8f9  mov     [rsp+0B00h+var_AC8], r13
0x14002b8fe  lea     rax, [rbp+0A00h+var_A60]
0x14002b902  mov     dword ptr [rsp+0B00h+var_AD0], 104h
0x14002b90a  mov     r8d, 0FFFFh
0x14002b910  mov     qword ptr [rsp+0B00h+ulFlags], rax
0x14002b915  xor     r9d, r9d
0x14002b918  mov     rdx, rbx
0x14002b91b  mov     dword ptr [rsp+0B00h+PropertyBufferSize], 1
0x14002b923  mov     rcx, r12
0x14002b926  call    cs:__imp_DriverStoreFindW
0x14002b92c  test    eax, eax
0x14002b92e  jnz     short loc_14002B93B
0x14002b930  lea     edi, [rsi+1]
0x14002b933  mov     ebx, r13d
0x14002b936  jmp     loc_14002BCF9
0x14002b93b  lea     rsi, [rbp+0A00h+var_A60]
0x14002b93f  mov     [rsp+0B00h+var_AC0], r13d
0x14002b944  lea     rax, [rsp+0B00h+var_AB0]
0x14002b949  mov     [rsp+0B00h+var_AC8], rax
0x14002b94e  lea     r9, DEVPKEY_DriverPackage_ClassGuid
0x14002b955  mov     ebx, 10h
0x14002b95a  lea     rax, [rbp+0A00h+Buf1]
0x14002b95e  mov     dword ptr [rsp+0B00h+var_AD0], ebx
0x14002b962  mov     r8, rsi
0x14002b965  mov     qword ptr [rsp+0B00h+ulFlags], rax
0x14002b96a  mov     rcx, r12
0x14002b96d  lea     rax, [rsp+0B00h+PropertyType]
0x14002b972  lea     esi, [rbx-0Eh]
0x14002b975  mov     [rsp+0B00h+PropertyBufferSize], rax
0x14002b97a  mov     edx, esi
0x14002b97c  call    cs:__imp_DriverStoreGetObjectPropertyW
0x14002b982  test    eax, eax
0x14002b984  jz      loc_14002BCD5
0x14002b98a  cmp     [rsp+0B00h+var_AB0], ebx
0x14002b98e  jnz     loc_14002BCD5
0x14002b994  cmp     [rsp+0B00h+PropertyType], 0Dh
0x14002b999  jnz     loc_14002BCD5
0x14002b99f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2> `wil::Feature<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::GetImpl(void)'::`2'::impl
0x14002b9a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverSetup_ReofferFingerprinting_v2>::__private_IsEnabled(void)
0x14002b9ab  lea     rdx, GUID_DEVCLASS_EXTENSION; Buf2
0x14002b9b2  lea     rcx, [rbp+0A00h+Buf1]; Buf1
0x14002b9b6  test    al, al
0x14002b9b8  jz      short loc_14002B9EC
0x14002b9ba  mov     r8d, ebx; Size
0x14002b9bd  mov     qword ptr [rsp+0B00h+var_A88], r12
0x14002b9c2  mov     dword ptr [rbp+0A00h+var_A88+8], r13d
0x14002b9c6  mov     [rbp+0A00h+var_A78], r14
0x14002b9ca  call    memcmp_0
0x14002b9cf  test    eax, eax
0x14002b9d1  lea     r9, [rsp+0B00h+var_A88]
0x14002b9d6  mov     edx, r13d
0x14002b9d9  mov     ecx, r15d; unsigned int
0x14002b9dc  setz    dl
0x14002b9df  call    DevUtilsDeviceEnumDeviceIds
0x14002b9e4  mov     ebx, dword ptr [rbp+0A00h+var_A88+8]
0x14002b9e7  jmp     loc_14002BCF9
0x14002b9ec  mov     r8d, 10h; Size
0x14002b9f2  mov     ebx, r13d
0x14002b9f5  call    memcmp_0
0x14002b9fa  test    eax, eax
0x14002b9fc  mov     ecx, esi
0x14002b9fe  mov     edx, 3
0x14002ba03  cmovz   ecx, edx
0x14002ba06  xor     esi, esi
0x14002ba08  mov     [rsp+0B00h+var_A94], ecx
0x14002ba0c  xor     edx, edx; Val
0x14002ba0e  lea     rcx, [rbp+0A00h+PropertyBuffer]; void *
0x14002ba15  mov     r8d, 800h; Size
0x14002ba1b  call    memset_0
0x14002ba20  lea     rcx, off_140048970
0x14002ba27  mov     r14d, r13d
0x14002ba2a  lea     rax, [rsp+0B00h+var_AB0]
0x14002ba2f  mov     [rsp+0B00h+ulFlags], esi; ulFlags
0x14002ba33  lea     r9, [rbp+0A00h+PropertyBuffer]; PropertyBuffer
0x14002ba3a  mov     [rsp+0B00h+var_AB0], 800h
0x14002ba42  lea     r8, [rsp+0B00h+PropertyType]; PropertyType
0x14002ba47  mov     [rsp+0B00h+PropertyBufferSize], rax; PropertyBufferSize
0x14002ba4c  mov     rdx, [rcx+r14*8]; PropertyKey
0x14002ba50  mov     ecx, r15d; dnDevInst
0x14002ba53  call    cs:__imp_CM_Get_DevNode_PropertyW
0x14002ba59  mov     esi, eax
0x14002ba5b  cmp     eax, 1Ah
0x14002ba5e  jnz     loc_14002BB17
0x14002ba64  cmp     r13d, 2
0x14002ba68  jb      loc_14002BC9A
0x14002ba6e  mov     eax, [rsp+0B00h+var_AB0]
0x14002ba72  cmp     eax, 800h
0x14002ba77  jbe     loc_14002BC9A
0x14002ba7d  cmp     [rsp+0B00h+PropertyType], 2012h
0x14002ba85  jnz     loc_14002BC9A
0x14002ba8b  mov     rcx, cs:hHeap; hHeap
0x14002ba92  lea     r8d, [rax+4]; dwBytes
0x14002ba96  xor     edx, edx; dwFlags
0x14002ba98  call    cs:__imp_HeapAlloc
0x14002ba9e  xor     esi, esi
0x14002baa0  mov     rdi, rax
0x14002baa3  test    rax, rax
0x14002baa6  jz      loc_14002BC9C
0x14002baac  mov     r8d, [rsp+0B00h+var_AB0]
0x14002bab1  xor     edx, edx; Val
0x14002bab3  add     r8, 4; Size
0x14002bab7  mov     rcx, rax; void *
0x14002baba  call    memset_0
0x14002babf  lea     rax, [rsp+0B00h+var_AB0]
0x14002bac4  mov     [rsp+0B00h+ulFlags], esi; ulFlags
0x14002bac8  lea     rdx, off_140048970
0x14002bacf  mov     [rsp+0B00h+PropertyBufferSize], rax; PropertyBufferSize
0x14002bad4  mov     rdx, [rdx+r14*8]; PropertyKey
0x14002bad8  lea     r8, [rsp+0B00h+PropertyType]; PropertyType
0x14002badd  mov     r9, rdi; PropertyBuffer
0x14002bae0  mov     ecx, r15d; dnDevInst
0x14002bae3  call    cs:__imp_CM_Get_DevNode_PropertyW
0x14002bae9  test    eax, eax
0x14002baeb  jnz     short loc_14002BAFD
0x14002baed  cmp     [rsp+0B00h+PropertyType], 2012h
0x14002baf5  jnz     short loc_14002BAFD
0x14002baf7  mov     ecx, [rsp+0B00h+var_AB0]
0x14002bafb  jmp     short loc_14002BB55
0x14002bafd  mov     rcx, cs:hHeap; hHeap
0x14002bb04  mov     r8, rdi; lpMem
0x14002bb07  xor     edx, edx; dwFlags
0x14002bb09  call    cs:__imp_HeapFree
0x14002bb0f  mov     rdi, rsi
0x14002bb12  jmp     loc_14002BC9C
0x14002bb17  test    esi, esi
0x14002bb19  jnz     loc_14002BC6C
0x14002bb1f  mov     esi, [rsp+0B00h+PropertyType]
0x14002bb23  cmp     esi, 2012h
0x14002bb29  jz      short loc_14002BB3D
0x14002bb2b  call    cs:__imp_DevRtlGetThreadLogToken
0x14002bb31  lea     r9, aDeviceProperty; "Device property index %d is of unexpect"...
0x14002bb38  jmp     loc_14002BC7E
0x14002bb3d  mov     ecx, 800h
0x14002bb42  lea     rdi, [rbp+0A00h+PropertyBuffer]
0x14002bb49  xor     esi, esi
0x14002bb4b  mov     [rsp+0B00h+var_AB0], ecx
0x14002bb4f  mov     [rbp+0A00h+var_54], esi
0x14002bb55  mov     r15d, ecx
0x14002bb58  mov     r14, rdi
0x14002bb5b  and     r15, 0FFFFFFFFFFFFFFFEh
0x14002bb5f  add     r15, rdi
0x14002bb62  cmp     rdi, r15
0x14002bb65  jnb     loc_14002BC3B
0x14002bb6b  cmp     [r14], si
0x14002bb6f  jz      loc_14002BC3B
0x14002bb75  mov     rax, [rsp+0B00h+lpMem]
0x14002bb7a  test    rax, rax
0x14002bb7d  jz      short loc_14002BB96
0x14002bb7f  mov     rcx, cs:hHeap; hHeap
0x14002bb86  mov     r8, rax; lpMem
0x14002bb89  xor     edx, edx; dwFlags
0x14002bb8b  call    cs:__imp_HeapFree
0x14002bb91  mov     [rsp+0B00h+lpMem], rsi
0x14002bb96  lea     rax, [rsp+0B00h+var_AB0]
0x14002bb9b  mov     r8, r14
0x14002bb9e  mov     [rsp+0B00h+var_AD0], rax
0x14002bba3  mov     rcx, r12
0x14002bba6  lea     rax, [rsp+0B00h+lpMem]
0x14002bbab  mov     qword ptr [rsp+0B00h+ulFlags], rax
0x14002bbb0  lea     rax, [rsp+0B00h+PropertyType]
0x14002bbb5  mov     [rsp+0B00h+PropertyBufferSize], rax
0x14002bbba  call    DrvUtilsAllocDriverStoreProperty
0x14002bbbf  test    eax, eax
0x14002bbc1  jz      short loc_14002BC30
0x14002bbc3  cmp     [rsp+0B00h+var_AB0], 2
0x14002bbc8  jb      short loc_14002BC30
0x14002bbca  cmp     [rsp+0B00h+PropertyType], 2012h
0x14002bbd2  jnz     short loc_14002BC30
0x14002bbd4  mov     rsi, [rsp+0B00h+lpMem]
0x14002bbd9  xor     eax, eax
0x14002bbdb  cmp     [rsi], ax
0x14002bbde  jz      short loc_14002BC0D
0x14002bbe0  mov     rdx, [rsp+0B00h+String2]; String2
0x14002bbe5  mov     rcx, rsi; String1
0x14002bbe8  call    _wcsicmp_0
0x14002bbed  xor     ecx, ecx
0x14002bbef  test    eax, eax
0x14002bbf1  jz      short loc_14002BC34
0x14002bbf3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002bbf7  inc     rax
0x14002bbfa  cmp     [rsi+rax*2], cx
0x14002bbfe  jnz     short loc_14002BBF7
0x14002bc00  lea     rsi, [rsi+rax*2]
0x14002bc04  add     rsi, 2
0x14002bc08  cmp     [rsi], cx
0x14002bc0b  jnz     short loc_14002BBE0
0x14002bc0d  xor     esi, esi
0x14002bc0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002bc13  inc     rax
0x14002bc16  cmp     [r14+rax*2], si
0x14002bc1b  jnz     short loc_14002BC13
0x14002bc1d  lea     r14, [r14+rax*2]
0x14002bc21  add     r14, 2
0x14002bc25  cmp     r14, r15
0x14002bc28  jb      loc_14002BB6B
0x14002bc2e  jmp     short loc_14002BC3B
0x14002bc30  mov     ebx, esi
0x14002bc32  jmp     short loc_14002BC0F
0x14002bc34  mov     ebx, 1
0x14002bc39  xor     esi, esi
0x14002bc3b  test    rdi, rdi
0x14002bc3e  jz      short loc_14002BC61
0x14002bc40  lea     rax, [rbp+0A00h+PropertyBuffer]
0x14002bc47  cmp     rdi, rax
0x14002bc4a  jz      short loc_14002BC61
0x14002bc4c  mov     rcx, cs:hHeap; hHeap
0x14002bc53  mov     r8, rdi; lpMem
0x14002bc56  xor     edx, edx; dwFlags
0x14002bc58  call    cs:__imp_HeapFree
0x14002bc5e  mov     rdi, rsi
0x14002bc61  test    ebx, ebx
0x14002bc63  jnz     short loc_14002BCAA
0x14002bc65  mov     r15d, [rsp+0B00h+var_A98]
0x14002bc6a  jmp     short loc_14002BC9C
0x14002bc6c  cmp     esi, 25h ; '%'
0x14002bc6f  jz      short loc_14002BC9A
0x14002bc71  call    cs:__imp_DevRtlGetThreadLogToken
0x14002bc77  lea     r9, aUnableToGetDev; "Unable to get device property index %d."...
0x14002bc7e  mov     r8d, 2
0x14002bc84  mov     [rsp+0B00h+ulFlags], esi
0x14002bc88  mov     rcx, rax
0x14002bc8b  mov     dword ptr [rsp+0B00h+PropertyBufferSize], r13d
0x14002bc90  lea     edx, [r8-1]
0x14002bc94  call    cs:__imp_DevRtlWriteTextLog
0x14002bc9a  xor     esi, esi
0x14002bc9c  inc     r13d
  ... truncated ...
```
