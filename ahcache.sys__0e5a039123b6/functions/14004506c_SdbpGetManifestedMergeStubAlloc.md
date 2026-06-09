# SdbpGetManifestedMergeStubAlloc

- ea: `0x14004506c`
- end: `0x140045456`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1002`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140041638`
- `0x140041d6c`

## callees

- `0x140004469`
- `0x14000448d`
- `0x1400044f9`
- `0x140004553`
- `0x14003e364`
- `0x14003e76c`
- `0x140040310`
- `0x14004506c`
- `0x140045d44`
- `0x140046180`
- `0x140046440`

## import_xrefs

- `ntoskrnl!ZwEnumerateValueKey` at `0x14004516e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140045284`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14004516e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140045284`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x1400452ad`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x1400452ad`

## string_xrefs

- `0x1400450db`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x140045208`: `SdbpGetManifestedMergeStubAlloc`
- `0x140045356`: `SdbpGetManifestedMergeStubAlloc`
- `0x14004539c`: `SdbpGetManifestedMergeStubAlloc`
- `0x1400452fe`: `Failed to allocate or convert stub path.`
- `0x14004538b`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x140045416`: `Failed to duplicate stub path.`
- `0x140045428`: `Failed to allocate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  ULONG v2; // r12d
  __int64 Pool2_0; // r13
  wchar_t *v5; // r15
  int MergeSdbsDisabled; // eax
  HANDLE v7; // rcx
  int v8; // ebx
  int Key; // eax
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rax
  ULONG Length; // ebx
  NTSTATUS v14; // eax
  __int64 v15; // rax
  ULONG v16; // ebx
  unsigned __int64 v17; // r14
  const char *v18; // r9
  __int64 v19; // r8
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v22; // rbx
  size_t v23; // r8
  void *v24; // rax
  void *v25; // [rsp+30h] [rbp-10h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-8h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+50h] BYREF
  ULONG v29; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v29 = 0;
  ResultLength = 0;
  v25 = 0;
  KeyHandle = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  Pool2_0 = 0;
  v5 = 0;
  MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v29);
  v8 = MergeSdbsDisabled;
  if ( MergeSdbsDisabled < 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetManifestedMergeStubAlloc",
      1186,
      "SdbpGetMergeSdbsDisabled failed [%x]",
      MergeSdbsDisabled);
  }
  else if ( v29 )
  {
    v8 = -1073741772;
  }
  else
  {
    Key = AslRegistryGetKey(
            &KeyHandle,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
            0x80000100,
            1);
    v8 = Key;
    if ( Key < 0 )
    {
      if ( Key != -1073741772 )
        AslLogCallPrintf(
          1,
          "SdbpGetManifestedMergeStubAlloc",
          1202,
          "AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]",
          Key);
    }
    else
    {
      v10 = 1;
      while ( wcsicmp_0(a2, (const wchar_t *)qword_14000A558[4 * v10]) )
      {
        if ( (int)++v10 >= 10 )
          goto LABEL_47;
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      Length = 2 * v12 + 18;
      v29 = Length;
      Pool2_0 = ExAllocatePool2_0(256, Length, 1953517633);
      if ( Pool2_0 )
      {
        while ( 1 )
        {
          v14 = ZwEnumerateValueKey(KeyHandle, v2, KeyValuePartialInformation, (PVOID)Pool2_0, Length, &ResultLength);
          v8 = v14;
          if ( v14 == -2147483622 )
            break;
          if ( v14 != -2147483643 && v14 != -1073741789 )
          {
            if ( v14 < 0 )
            {
              AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1241, "Failed to query partial info.");
              goto LABEL_21;
            }
            if ( *(_DWORD *)(Pool2_0 + 4) == 1 && !wcsicmp_0(a2, (const wchar_t *)(Pool2_0 + 12)) )
            {
              v15 = -1;
              do
                ++v15;
              while ( a2[v15] );
              v16 = 2 * v15 + 538;
              v17 = v16;
              v5 = (wchar_t *)ExAllocatePool2_0(256, v16, 1953517633);
              if ( !v5 )
              {
                v18 = "Failed to allocate basic info.";
                v19 = 1258;
                goto LABEL_20;
              }
              v8 = ZwEnumerateValueKey(KeyHandle, v2, KeyValueBasicInformation, v5, v16, &ResultLength);
              if ( v8 < 0 )
              {
                AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1269, "Failed to query basic info.");
                goto LABEL_21;
              }
              if ( (unsigned __int64)ResultLength + 2 > v17 )
              {
                v8 = -1073741789;
                AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1274, "Buffer too small to query basic info.");
                goto LABEL_21;
              }
              NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot();
              v22 = NtSystemRoot;
              v23 = -1;
              do
                ++v23;
              while ( NtSystemRoot[v23] );
              if ( wcsnicmp_0(NtSystemRoot, v5 + 6, v23) )
              {
                v8 = AslStringDuplicate(&v25, v5 + 6);
                if ( v8 < 0 )
                {
                  AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1301, "Failed to duplicate stub path.");
                  goto LABEL_21;
                }
              }
              else
              {
                do
                  ++v11;
                while ( v22[v11] );
                v8 = AslPathToSystemPath(&v25, (__int64)&v5[v11 + 6]);
                if ( v8 < 0 )
                {
                  AslLogCallPrintf(
                    1,
                    "SdbpGetManifestedMergeStubAlloc",
                    1294,
                    "Failed to allocate or convert stub path.");
                  goto LABEL_21;
                }
              }
              v24 = v25;
              if ( v25 )
              {
                v8 = 0;
                v25 = 0;
                *a1 = v24;
                goto LABEL_21;
              }
              v18 = "Failed to allocate stub path.";
              v19 = 1308;
              goto LABEL_20;
            }
          }
          Length = v29;
          ++v2;
        }
LABEL_47:
        v8 = -1073741772;
        goto LABEL_21;
      }
      v18 = "Failed to allocate partial info.";
      v19 = 1222;
LABEL_20:
      v8 = -1073741801;
      AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", v19, v18);
    }
LABEL_21:
    v7 = KeyHandle;
    if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      ZwClose_0(KeyHandle);
  }
  if ( v25 )
    AslFree((__int64)v7, v25);
  if ( Pool2_0 )
    AslFree((__int64)v7, (void *)Pool2_0);
  if ( v5 )
    AslFree((__int64)v7, v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004506c  mov     [rsp-38h+arg_8], rbx
0x140045071  mov     [rsp-38h+arg_0], rcx
0x140045076  push    rbp
0x140045077  push    rsi
0x140045078  push    rdi
0x140045079  push    r12
0x14004507b  push    r13
0x14004507d  push    r14
0x14004507f  push    r15
0x140045081  mov     rbp, rsp
0x140045084  sub     rsp, 40h
0x140045088  xor     r12d, r12d
0x14004508b  mov     r14, rdx
0x14004508e  mov     [rbp+arg_18], r12d
0x140045092  mov     [rbp+arg_10], r12d
0x140045096  mov     [rbp+var_10], r12
0x14004509a  mov     [rbp+KeyHandle], r12
0x14004509e  test    rcx, rcx
0x1400450a1  jz      loc_14004536C
0x1400450a7  mov     [rcx], r12
0x1400450aa  mov     r13d, r12d
0x1400450ad  lea     rcx, [rbp+arg_18]
0x1400450b1  mov     r15d, r12d
0x1400450b4  call    SdbpGetMergeSdbsDisabled
0x1400450b9  mov     ebx, eax
0x1400450bb  test    eax, eax
0x1400450bd  js      loc_140045345
0x1400450c3  cmp     [rbp+arg_18], r12d
0x1400450c7  jnz     loc_140045376
0x1400450cd  lea     edi, [r12+1]
0x1400450d2  mov     r8d, 80000100h
0x1400450d8  mov     r9d, edi
0x1400450db  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400450e2  lea     rcx, [rbp+KeyHandle]
0x1400450e6  call    AslRegistryGetKey
0x1400450eb  mov     ebx, eax
0x1400450ed  test    eax, eax
0x1400450ef  js      loc_140045380
0x1400450f5  mov     ebx, edi
0x1400450f7  lea     rax, qword_14000A558
0x1400450fe  mov     edx, ebx
0x140045100  shl     rdx, 5
0x140045104  mov     rcx, r14; Str1
0x140045107  mov     rdx, [rdx+rax]; Str2
0x14004510b  call    _wcsicmp_0
0x140045110  test    eax, eax
0x140045112  jnz     loc_1400453AF
0x140045118  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14004511c  mov     rax, rsi
0x14004511f  inc     rax
0x140045122  cmp     [r14+rax*2], r12w
0x140045127  jnz     short loc_14004511F
0x140045129  lea     ebx, ds:12h[rax*2]
0x140045130  mov     ecx, 100h
0x140045135  mov     edx, ebx
0x140045137  mov     r8d, 74705041h
0x14004513d  mov     [rbp+arg_18], ebx
0x140045140  call    ExAllocatePool2_0
0x140045145  mov     r13, rax
0x140045148  test    rax, rax
0x14004514b  jz      loc_1400453C4
0x140045151  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140045155  lea     rax, [rbp+arg_10]
0x140045159  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14004515e  mov     r9, r13; KeyValueInformation
0x140045161  mov     r8d, 2; KeyValueInformationClass
0x140045167  mov     [rsp+40h+Length], ebx; Length
0x14004516b  mov     edx, r12d; Index
0x14004516e  call    cs:__imp_ZwEnumerateValueKey
0x140045175  nop     dword ptr [rax+rax+00h]
0x14004517a  mov     ebx, eax
0x14004517c  cmp     eax, 8000001Ah
0x140045181  jz      loc_1400453BA
0x140045187  cmp     eax, 80000005h
0x14004518c  jz      loc_14004533A
0x140045192  cmp     eax, 0C0000023h
0x140045197  jz      loc_14004533A
0x14004519d  test    eax, eax
0x14004519f  js      loc_14004543A
0x1400451a5  cmp     [r13+4], edi
0x1400451a9  jnz     loc_14004533A
0x1400451af  lea     rdx, [r13+0Ch]; Str2
0x1400451b3  mov     rcx, r14; Str1
0x1400451b6  call    _wcsicmp_0
0x1400451bb  xor     ecx, ecx
0x1400451bd  test    eax, eax
0x1400451bf  jnz     loc_14004533A
0x1400451c5  mov     rax, rsi
0x1400451c8  inc     rax
0x1400451cb  cmp     [r14+rax*2], cx
0x1400451d0  jnz     short loc_1400451C8
0x1400451d2  lea     ebx, ds:21Ah[rax*2]
0x1400451d9  mov     r8d, 74705041h
0x1400451df  mov     edx, ebx
0x1400451e1  mov     ecx, 100h
0x1400451e6  mov     r14d, ebx
0x1400451e9  call    ExAllocatePool2_0
0x1400451ee  mov     r15, rax
0x1400451f1  test    rax, rax
0x1400451f4  jnz     short loc_14004526A
0x1400451f6  lea     r9, aFailedToAlloca_12; "Failed to allocate basic info."
0x1400451fd  mov     r8d, 4EAh
0x140045203  mov     ebx, 0C0000017h
0x140045208  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x14004520f  mov     ecx, edi
0x140045211  call    AslLogCallPrintf
0x140045216  mov     rcx, [rbp+KeyHandle]; Handle
0x14004521a  lea     rax, [rcx-1]
0x14004521e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140045222  jbe     loc_140045330
0x140045228  mov     rdx, [rbp+var_10]
0x14004522c  test    rdx, rdx
0x14004522f  jnz     loc_14004544C
0x140045235  test    r13, r13
0x140045238  jz      short loc_140045242
0x14004523a  mov     rdx, r13
0x14004523d  call    AslFree
0x140045242  test    r15, r15
0x140045245  jz      short loc_14004524F
0x140045247  mov     rdx, r15
0x14004524a  call    AslFree
0x14004524f  mov     eax, ebx
0x140045251  mov     rbx, [rsp+40h+arg_8]
0x140045259  add     rsp, 40h
0x14004525d  pop     r15
0x14004525f  pop     r14
0x140045261  pop     r13
0x140045263  pop     r12
0x140045265  pop     rdi
0x140045266  pop     rsi
0x140045267  pop     rbp
0x140045268  retn
0x14004526a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14004526e  lea     rax, [rbp+arg_10]
0x140045272  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140045277  mov     r9, r15; KeyValueInformation
0x14004527a  xor     r8d, r8d; KeyValueInformationClass
0x14004527d  mov     [rsp+40h+Length], ebx; Length
0x140045281  mov     edx, r12d; Index
0x140045284  call    cs:__imp_ZwEnumerateValueKey
0x14004528b  nop     dword ptr [rax+rax+00h]
0x140045290  xor     r12d, r12d
0x140045293  mov     ebx, eax
0x140045295  test    eax, eax
0x140045297  js      loc_1400453D6
0x14004529d  mov     eax, [rbp+arg_10]
0x1400452a0  add     rax, 2
0x1400452a4  cmp     rax, r14
0x1400452a7  ja      loc_1400453E8
0x1400452ad  call    cs:__imp_RtlGetNtSystemRoot
0x1400452b4  nop     dword ptr [rax+rax+00h]
0x1400452b9  mov     rbx, rax
0x1400452bc  mov     r8, rsi
0x1400452bf  inc     r8; MaxCount
0x1400452c2  cmp     [rax+r8*2], r12w
0x1400452c7  jnz     short loc_1400452BF
0x1400452c9  lea     rdx, [r15+0Ch]; Str2
0x1400452cd  mov     rcx, rbx; Str1
0x1400452d0  call    _wcsnicmp_0
0x1400452d5  test    eax, eax
0x1400452d7  jnz     loc_1400453FF
0x1400452dd  inc     rsi
0x1400452e0  cmp     [rbx+rsi*2], r12w
0x1400452e5  jnz     short loc_1400452DD
0x1400452e7  lea     rdx, [rsi+6]
0x1400452eb  lea     rdx, [r15+rdx*2]
0x1400452ef  lea     rcx, [rbp+var_10]
0x1400452f3  call    AslPathToSystemPath
0x1400452f8  mov     ebx, eax
0x1400452fa  test    eax, eax
0x1400452fc  jns     short loc_140045310
0x1400452fe  lea     r9, aFailedToAlloca_7; "Failed to allocate or convert stub path"...
0x140045305  mov     r8d, 50Eh
0x14004530b  jmp     loc_140045208
0x140045310  mov     rax, [rbp+var_10]
0x140045314  test    rax, rax
0x140045317  jz      loc_140045428
0x14004531d  mov     rcx, [rbp+arg_0]
0x140045321  mov     ebx, r12d
0x140045324  mov     [rbp+var_10], r12
0x140045328  mov     [rcx], rax
0x14004532b  jmp     loc_140045216
0x140045330  call    ZwClose_0
0x140045335  jmp     loc_140045228
0x14004533a  mov     ebx, [rbp+arg_18]
0x14004533d  add     r12d, edi
0x140045340  jmp     loc_140045151
0x140045345  lea     r9, aSdbpgetmergesd; "SdbpGetMergeSdbsDisabled failed [%x]"
0x14004534c  mov     [rsp+40h+Length], eax
0x140045350  mov     r8d, 4A2h
0x140045356  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x14004535d  mov     ecx, 1
0x140045362  call    AslLogCallPrintf
0x140045367  jmp     loc_140045228
0x14004536c  mov     eax, 0C00000EFh
0x140045371  jmp     loc_140045251
0x140045376  mov     ebx, 0C0000034h
0x14004537b  jmp     loc_140045228
0x140045380  cmp     eax, 0C0000034h
0x140045385  jz      loc_140045216
0x14004538b  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open Manife"...
0x140045392  mov     [rsp+40h+Length], eax
0x140045396  mov     r8d, 4B2h
0x14004539c  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1400453a3  mov     ecx, edi
0x1400453a5  call    AslLogCallPrintf
0x1400453aa  jmp     loc_140045216
0x1400453af  add     ebx, edi
0x1400453b1  cmp     ebx, 0Ah
0x1400453b4  jl      loc_1400450F7
0x1400453ba  mov     ebx, 0C0000034h
0x1400453bf  jmp     loc_140045216
0x1400453c4  lea     r9, aFailedToAlloca_2; "Failed to allocate partial info."
0x1400453cb  mov     r8d, 4C6h
0x1400453d1  jmp     loc_140045203
0x1400453d6  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x1400453dd  mov     r8d, 4F5h
0x1400453e3  jmp     loc_140045208
0x1400453e8  mov     ebx, 0C0000023h
0x1400453ed  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x1400453f4  mov     r8d, 4FAh
0x1400453fa  jmp     loc_140045208
0x1400453ff  lea     rdx, [r15+0Ch]
0x140045403  lea     rcx, [rbp+var_10]
0x140045407  call    AslStringDuplicate
0x14004540c  mov     ebx, eax
0x14004540e  test    eax, eax
0x140045410  jns     loc_140045310
0x140045416  lea     r9, aFailedToDuplic_0; "Failed to duplicate stub path."
0x14004541d  mov     r8d, 515h
0x140045423  jmp     loc_140045208
0x140045428  lea     r9, aFailedToAlloca_23; "Failed to allocate stub path."
0x14004542f  mov     r8d, 51Ch
0x140045435  jmp     loc_140045203
0x14004543a  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x140045441  mov     r8d, 4D9h
0x140045447  jmp     loc_140045208
0x14004544c  call    AslFree
0x140045451  jmp     loc_140045235
```
