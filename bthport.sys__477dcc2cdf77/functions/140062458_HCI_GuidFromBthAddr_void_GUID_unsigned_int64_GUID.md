# HCI_GuidFromBthAddr(void *,_GUID,unsigned __int64,_GUID *)

- ea: `0x140062458`
- end: `0x140062972`
- name: `?HCI_GuidFromBthAddr@@YAJPEAXU_GUID@@_KPEAU1@@Z`
- size: `1306`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject, struct _GUID *__struct_ptr, unsigned __int64, struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14005a290`
- `0x1400649d8`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005748`
- `0x140062458`
- `0x140165540`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006292f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062945`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006292f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062945`
- `ntoskrnl!ExAllocatePool2` at `0x14006258b`
- `ntoskrnl!ExAllocatePool2` at `0x140062816`
- `ntoskrnl!ExAllocatePool2` at `0x14006258b`
- `ntoskrnl!ExAllocatePool2` at `0x140062816`
- `ksecdd!BCryptGetProperty` at `0x1400624c8`
- `ksecdd!BCryptGetProperty` at `0x14006272e`
- `ksecdd!BCryptGetProperty` at `0x1400624c8`
- `ksecdd!BCryptGetProperty` at `0x14006272e`
- `ksecdd!BCryptCreateHash` at `0x140062613`
- `ksecdd!BCryptCreateHash` at `0x140062613`
- `ksecdd!BCryptHashData` at `0x14006266d`
- `ksecdd!BCryptHashData` at `0x1400626c4`
- `ksecdd!BCryptHashData` at `0x14006266d`
- `ksecdd!BCryptHashData` at `0x1400626c4`
- `ksecdd!BCryptFinishHash` at `0x140062872`
- `ksecdd!BCryptFinishHash` at `0x140062872`
- `ksecdd!BCryptDestroyHash` at `0x140062911`
- `ksecdd!BCryptDestroyHash` at `0x140062911`

## pseudocode

```c
__int64 __fastcall HCI_GuidFromBthAddr(BCRYPT_HANDLE hObject, struct _GUID *a2, __int64 a3, struct _GUID *a4)
{
  __int128 v4; // xmm0
  UCHAR *v6; // r15
  struct _GUID *v7; // r14
  ULONG v9; // edx
  NTSTATUS Property; // ebx
  ULONG v11; // r8d
  PDEVICE_OBJECT v12; // rcx
  PDEVICE_OBJECT v13; // rcx
  bool v14; // r10
  UCHAR *Pool2; // rax
  int v16; // edx
  int v17; // r8d
  PDEVICE_OBJECT v18; // r10
  bool v19; // r10
  UCHAR *v20; // rax
  __int16 v22; // [rsp+30h] [rbp-39h]
  __int16 v23; // [rsp+30h] [rbp-39h]
  __int16 v24; // [rsp+30h] [rbp-39h]
  char v25; // [rsp+40h] [rbp-29h]
  char v26; // [rsp+40h] [rbp-29h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-19h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-15h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-11h] BYREF
  UCHAR v30[16]; // [rsp+60h] [rbp-9h] BYREF
  UCHAR pbInput[16]; // [rsp+70h] [rbp+7h] BYREF

  v4 = (__int128)*a2;
  *(_QWORD *)v30 = a3;
  phHash = 0;
  v6 = 0;
  *(_DWORD *)pbOutput = 0;
  v7 = 0;
  pcbResult = 0;
  *(_OWORD *)pbInput = v4;
  Property = BCryptGetProperty(hObject, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 15;
LABEL_69:
    LOBYTE(v11) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      v12->AttachedDevice,
      v9,
      v11,
      v12->DeviceExtension,
      2,
      6,
      v22,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      v25);
    goto LABEL_70;
  }
  v9 = pcbResult;
  if ( pcbResult != 4 )
  {
    Property = -1073741306;
    v13 = WPP_GLOBAL_Control;
    v14 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v26 = pcbResult;
    LOBYTE(v9) = v14;
    v23 = 16;
LABEL_13:
    LOBYTE(v11) = 1;
    WPP_RECORDER_AND_TRACE_SF_LL(
      v13->AttachedDevice,
      v9,
      v11,
      v13->DeviceExtension,
      2,
      6,
      v23,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids,
      v26,
      4);
LABEL_70:
    *a4 = 0;
    goto LABEL_72;
  }
  Pool2 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)pbOutput, 1346917442);
  v6 = Pool2;
  if ( !Pool2 )
  {
    Property = -1073741670;
    v18 = WPP_GLOBAL_Control;
    LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v24 = 17;
LABEL_20:
    LOBYTE(v17) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v18->AttachedDevice,
      v16,
      v17,
      v18->DeviceExtension,
      2,
      6,
      v24,
      (__int64)WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids);
    goto LABEL_70;
  }
  Property = BCryptCreateHash(hObject, &phHash, Pool2, *(ULONG *)pbOutput, 0, 0, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 18;
    goto LABEL_69;
  }
  Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 19;
    goto LABEL_69;
  }
  Property = BCryptHashData(phHash, v30, 8u, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 20;
    goto LABEL_69;
  }
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 21;
    goto LABEL_69;
  }
  v11 = pcbResult;
  if ( pcbResult != 4 )
  {
    Property = -1073741811;
    v13 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v26 = pcbResult;
    v23 = 22;
    goto LABEL_13;
  }
  v9 = *(_DWORD *)pbOutput;
  if ( *(_DWORD *)pbOutput < 0x10u )
  {
    Property = -1073741811;
    v12 = WPP_GLOBAL_Control;
    v19 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = pbOutput[0];
    LOBYTE(v9) = v19;
    v22 = 23;
    goto LABEL_69;
  }
  v20 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)pbOutput, 1346917442);
  v7 = (struct _GUID *)v20;
  if ( !v20 )
  {
    Property = -1073741670;
    v18 = WPP_GLOBAL_Control;
    LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v24 = 24;
    goto LABEL_20;
  }
  Property = BCryptFinishHash(phHash, v20, *(ULONG *)pbOutput, 0);
  if ( Property < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v25 = Property;
    v22 = 25;
    goto LABEL_69;
  }
  *a4 = *v7;
  a4->Data3 = a4->Data3 & 0xFFF | 0x5000;
  a4->Data4[0] = a4->Data4[0] & 0x3F | 0x80;
LABEL_72:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140062458  push    rbp
0x14006245a  push    rbx
0x14006245b  push    rsi
0x14006245c  push    rdi
0x14006245d  push    r13
0x14006245f  push    r14
0x140062461  push    r15
0x140062463  lea     rbp, [rsp-27h]
0x140062468  sub     rsp, 90h
0x14006246f  mov     rax, cs:__security_cookie
0x140062476  xor     rax, rsp
0x140062479  mov     [rbp+57h+var_40], rax
0x14006247d  movups  xmm0, xmmword ptr [rdx]
0x140062480  mov     r13, r9
0x140062483  mov     qword ptr [rbp+57h+var_60], r8
0x140062487  lea     rax, [rbp+57h+var_6C]
0x14006248b  mov     [rbp+57h+phHash], 0
0x140062493  xor     r15d, r15d
0x140062496  mov     dword ptr [rbp+57h+pbOutput], 0
0x14006249d  xor     r14d, r14d
0x1400624a0  mov     [rbp+57h+var_6C], 0
0x1400624a7  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x1400624ac  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1400624b0  lea     rdx, pszProperty; "ObjectLength"
0x1400624b7  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x1400624bc  lea     r9d, [r15+4]; cbOutput
0x1400624c0  mov     rsi, rcx
0x1400624c3  movdqu  xmmword ptr [rbp+57h+pbInput], xmm0
0x1400624c8  call    cs:__imp_BCryptGetProperty
0x1400624cf  nop     dword ptr [rax+rax+00h]
0x1400624d4  mov     ebx, eax
0x1400624d6  test    eax, eax
0x1400624d8  jns     short loc_140062510
0x1400624da  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400624e1  mov     eax, [rcx+2Ch]
0x1400624e4  test    al, 20h
0x1400624e6  jz      short loc_1400624F2
0x1400624e8  cmp     byte ptr [rcx+29h], 2
0x1400624ec  jb      short loc_1400624F2
0x1400624ee  mov     dl, 1
0x1400624f0  jmp     short loc_1400624F4
0x1400624f2  xor     dl, dl
0x1400624f4  mov     dword ptr [rsp+0C0h+var_80], ebx
0x1400624f8  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400624ff  mov     [rsp+0C0h+var_88], rax
0x140062504  mov     [rsp+0C0h+var_90], 0Fh
0x14006250b  jmp     loc_1400628B5
0x140062510  mov     edx, [rbp+57h+var_6C]
0x140062513  cmp     edx, 4
0x140062516  jz      short loc_14006257D
0x140062518  mov     ebx, 0C0000206h
0x14006251d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140062524  mov     eax, [rcx+2Ch]
0x140062527  test    al, 20h
0x140062529  jz      short loc_140062536
0x14006252b  cmp     byte ptr [rcx+29h], 2
0x14006252f  jb      short loc_140062536
0x140062531  mov     r10b, 1
0x140062534  jmp     short loc_140062539
0x140062536  xor     r10b, r10b
0x140062539  mov     [rsp+0C0h+var_78], 4
0x140062541  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140062548  mov     dword ptr [rsp+0C0h+var_80], edx
0x14006254c  mov     dl, r10b
0x14006254f  mov     [rsp+0C0h+var_88], rax
0x140062554  mov     [rsp+0C0h+var_90], 10h
0x14006255b  mov     r9, [rcx+40h]
0x14006255f  mov     r8b, 1
0x140062562  mov     rcx, [rcx+18h]
0x140062566  mov     [rsp+0C0h+dwFlags], 6
0x14006256e  mov     byte ptr [rsp+0C0h+pcbResult], 2
0x140062573  call    WPP_RECORDER_AND_TRACE_SF_LL
0x140062578  jmp     loc_1400628D2
0x14006257d  mov     edx, dword ptr [rbp+57h+pbOutput]
0x140062580  mov     ecx, 40h ; '@'
0x140062585  mov     r8d, 50485442h
0x14006258b  call    cs:__imp_ExAllocatePool2
0x140062592  nop     dword ptr [rax+rax+00h]
0x140062597  mov     r15, rax
0x14006259a  test    rax, rax
0x14006259d  jnz     short loc_1400625F6
0x14006259f  mov     ebx, 0C000009Ah
0x1400625a4  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400625ab  mov     ecx, [r10+2Ch]
0x1400625af  test    cl, 20h
0x1400625b2  jz      short loc_1400625BF
0x1400625b4  cmp     byte ptr [r10+29h], 2
0x1400625b9  jb      short loc_1400625BF
0x1400625bb  mov     dl, 1
0x1400625bd  jmp     short loc_1400625C1
0x1400625bf  xor     dl, dl
0x1400625c1  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400625c8  mov     [rsp+0C0h+var_88], rax
0x1400625cd  mov     [rsp+0C0h+var_90], 11h
0x1400625d4  mov     r9, [r10+40h]
0x1400625d8  mov     r8b, 1
0x1400625db  mov     rcx, [r10+18h]
0x1400625df  mov     [rsp+0C0h+dwFlags], 6
0x1400625e7  mov     byte ptr [rsp+0C0h+pcbResult], 2
0x1400625ec  call    WPP_RECORDER_AND_TRACE_SF_
0x1400625f1  jmp     loc_1400628D2
0x1400625f6  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1400625fa  lea     rdx, [rbp+57h+phHash]; phHash
0x1400625fe  mov     dword ptr [rsp+0C0h+var_90], r14d; dwFlags
0x140062603  mov     r8, rax; pbHashObject
0x140062606  mov     [rsp+0C0h+dwFlags], r14d; cbSecret
0x14006260b  mov     rcx, rsi; hAlgorithm
0x14006260e  mov     [rsp+0C0h+pcbResult], r14; pbSecret
0x140062613  call    cs:__imp_BCryptCreateHash
0x14006261a  nop     dword ptr [rax+rax+00h]
0x14006261f  mov     ebx, eax
0x140062621  test    eax, eax
0x140062623  jns     short loc_14006265B
0x140062625  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006262c  mov     eax, [rcx+2Ch]
0x14006262f  test    al, 20h
0x140062631  jz      short loc_14006263D
0x140062633  cmp     byte ptr [rcx+29h], 2
0x140062637  jb      short loc_14006263D
0x140062639  mov     dl, 1
0x14006263b  jmp     short loc_14006263F
0x14006263d  xor     dl, dl
0x14006263f  mov     dword ptr [rsp+0C0h+var_80], ebx
0x140062643  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x14006264a  mov     [rsp+0C0h+var_88], rax
0x14006264f  mov     [rsp+0C0h+var_90], 12h
0x140062656  jmp     loc_1400628B5
0x14006265b  mov     rcx, [rbp+57h+phHash]; hHash
0x14006265f  lea     rdx, [rbp+57h+pbInput]; pbInput
0x140062663  xor     r9d, r9d; dwFlags
0x140062666  lea     edi, [r9+10h]
0x14006266a  mov     r8d, edi; cbInput
0x14006266d  call    cs:__imp_BCryptHashData
0x140062674  nop     dword ptr [rax+rax+00h]
0x140062679  mov     ebx, eax
0x14006267b  test    eax, eax
0x14006267d  jns     short loc_1400626B5
0x14006267f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140062686  mov     eax, [rcx+2Ch]
0x140062689  test    al, 20h
0x14006268b  jz      short loc_140062697
0x14006268d  cmp     byte ptr [rcx+29h], 2
0x140062691  jb      short loc_140062697
0x140062693  mov     dl, 1
0x140062695  jmp     short loc_140062699
0x140062697  xor     dl, dl
0x140062699  mov     dword ptr [rsp+0C0h+var_80], ebx
0x14006269d  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400626a4  mov     [rsp+0C0h+var_88], rax
0x1400626a9  mov     [rsp+0C0h+var_90], 13h
0x1400626b0  jmp     loc_1400628B5
0x1400626b5  mov     rcx, [rbp+57h+phHash]; hHash
0x1400626b9  lea     rdx, [rbp+57h+var_60]; pbInput
0x1400626bd  xor     r9d, r9d; dwFlags
0x1400626c0  lea     r8d, [r9+8]; cbInput
0x1400626c4  call    cs:__imp_BCryptHashData
0x1400626cb  nop     dword ptr [rax+rax+00h]
0x1400626d0  mov     ebx, eax
0x1400626d2  test    eax, eax
0x1400626d4  jns     short loc_14006270C
0x1400626d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400626dd  mov     eax, [rcx+2Ch]
0x1400626e0  test    al, 20h
0x1400626e2  jz      short loc_1400626EE
0x1400626e4  cmp     byte ptr [rcx+29h], 2
0x1400626e8  jb      short loc_1400626EE
0x1400626ea  mov     dl, 1
0x1400626ec  jmp     short loc_1400626F0
0x1400626ee  xor     dl, dl
0x1400626f0  mov     dword ptr [rsp+0C0h+var_80], ebx
0x1400626f4  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400626fb  mov     [rsp+0C0h+var_88], rax
0x140062700  mov     [rsp+0C0h+var_90], 14h
0x140062707  jmp     loc_1400628B5
0x14006270c  lea     rax, [rbp+57h+var_6C]
0x140062710  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x140062715  mov     r9d, 4; cbOutput
0x14006271b  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x140062720  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x140062724  mov     rcx, rsi; hObject
0x140062727  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14006272e  call    cs:__imp_BCryptGetProperty
0x140062735  nop     dword ptr [rax+rax+00h]
0x14006273a  mov     ebx, eax
0x14006273c  test    eax, eax
0x14006273e  jns     short loc_140062776
0x140062740  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140062747  mov     eax, [rcx+2Ch]
0x14006274a  test    al, 20h
0x14006274c  jz      short loc_140062758
0x14006274e  cmp     byte ptr [rcx+29h], 2
0x140062752  jb      short loc_140062758
0x140062754  mov     dl, 1
0x140062756  jmp     short loc_14006275A
0x140062758  xor     dl, dl
0x14006275a  mov     dword ptr [rsp+0C0h+var_80], ebx
0x14006275e  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140062765  mov     [rsp+0C0h+var_88], rax
0x14006276a  mov     [rsp+0C0h+var_90], 15h
0x140062771  jmp     loc_1400628B5
0x140062776  mov     r8d, [rbp+57h+var_6C]
0x14006277a  cmp     r8d, 4
0x14006277e  jz      short loc_1400627C4
0x140062780  mov     ebx, 0C000000Dh
0x140062785  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006278c  mov     eax, [rcx+2Ch]
0x14006278f  test    al, 20h
0x140062791  jz      short loc_14006279D
0x140062793  cmp     byte ptr [rcx+29h], 2
0x140062797  jb      short loc_14006279D
0x140062799  mov     dl, 1
0x14006279b  jmp     short loc_14006279F
0x14006279d  xor     dl, dl
0x14006279f  mov     [rsp+0C0h+var_78], 4
0x1400627a7  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400627ae  mov     dword ptr [rsp+0C0h+var_80], r8d
0x1400627b3  mov     [rsp+0C0h+var_88], rax
0x1400627b8  mov     [rsp+0C0h+var_90], 16h
0x1400627bf  jmp     loc_14006255B
0x1400627c4  mov     edx, dword ptr [rbp+57h+pbOutput]
0x1400627c7  cmp     edx, edi
0x1400627c9  jnb     short loc_14006280B
0x1400627cb  mov     ebx, 0C000000Dh
0x1400627d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400627d7  mov     eax, [rcx+2Ch]
0x1400627da  test    al, 20h
0x1400627dc  jz      short loc_1400627E9
0x1400627de  cmp     byte ptr [rcx+29h], 2
0x1400627e2  jb      short loc_1400627E9
0x1400627e4  mov     r10b, 1
0x1400627e7  jmp     short loc_1400627EC
0x1400627e9  xor     r10b, r10b
0x1400627ec  mov     dword ptr [rsp+0C0h+var_80], edx
0x1400627f0  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400627f7  mov     [rsp+0C0h+var_88], rax
0x1400627fc  mov     dl, r10b
0x1400627ff  mov     [rsp+0C0h+var_90], 17h
0x140062806  jmp     loc_1400628B5
0x14006280b  mov     ecx, 40h ; '@'
0x140062810  mov     r8d, 50485442h
0x140062816  call    cs:__imp_ExAllocatePool2
0x14006281d  nop     dword ptr [rax+rax+00h]
0x140062822  mov     r14, rax
0x140062825  test    rax, rax
0x140062828  jnz     short loc_140062864
0x14006282a  mov     ebx, 0C000009Ah
0x14006282f  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140062836  mov     ecx, [r10+2Ch]
0x14006283a  test    cl, 20h
0x14006283d  jz      short loc_14006284A
0x14006283f  cmp     byte ptr [r10+29h], 2
0x140062844  jb      short loc_14006284A
0x140062846  mov     dl, 1
0x140062848  jmp     short loc_14006284C
0x14006284a  xor     dl, dl
0x14006284c  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x140062853  mov     [rsp+0C0h+var_88], rax
0x140062858  mov     [rsp+0C0h+var_90], 18h
0x14006285f  jmp     loc_1400625D4
0x140062864  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x140062868  xor     r9d, r9d; dwFlags
0x14006286b  mov     rcx, [rbp+57h+phHash]; hHash
0x14006286f  mov     rdx, r14; pbOutput
0x140062872  call    cs:__imp_BCryptFinishHash
0x140062879  nop     dword ptr [rax+rax+00h]
0x14006287e  mov     ebx, eax
0x140062880  test    eax, eax
0x140062882  jns     short loc_1400628DC
0x140062884  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006288b  mov     eax, [rcx+2Ch]
0x14006288e  test    al, 20h
0x140062890  jz      short loc_14006289C
0x140062892  cmp     byte ptr [rcx+29h], 2
0x140062896  jb      short loc_14006289C
0x140062898  mov     dl, 1
0x14006289a  jmp     short loc_14006289E
0x14006289c  xor     dl, dl
0x14006289e  mov     dword ptr [rsp+0C0h+var_80], ebx
0x1400628a2  lea     rax, WPP_2c02b4fd26c4340466e34f5aad650b83_Traceguids
0x1400628a9  mov     [rsp+0C0h+var_88], rax
0x1400628ae  mov     [rsp+0C0h+var_90], 19h
0x1400628b5  mov     r9, [rcx+40h]
0x1400628b9  mov     r8b, 1
0x1400628bc  mov     rcx, [rcx+18h]
0x1400628c0  mov     [rsp+0C0h+dwFlags], 6
0x1400628c8  mov     byte ptr [rsp+0C0h+pcbResult], 2
0x1400628cd  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400628d2  xorps   xmm0, xmm0
0x1400628d5  movups  xmmword ptr [r13+0], xmm0
0x1400628da  jmp     short loc_140062908
0x1400628dc  movups  xmm0, xmmword ptr [r14]
0x1400628e0  mov     ecx, 0FFFh
0x1400628e5  movdqu  xmmword ptr [r13+0], xmm0
0x1400628eb  movzx   eax, word ptr [r13+6]
0x1400628f0  and     ax, cx
0x1400628f3  or      ax, 5000h
0x1400628f7  mov     [r13+6], ax
0x1400628fc  mov     al, [r13+8]
0x140062900  and     al, 3Fh
0x140062902  or      al, 80h
  ... truncated ...
```
