# GenericSetRegBeforeUpgMigrationShimCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x18003ad60`
- end: `0x18003b04c`
- name: `?GenericSetRegBeforeUpgMigrationShimCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `748`
- prototype: `int(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ad30`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x18003ad60`
- `0x18003b248`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x18003af13`
- `KERNEL32!RtlCompareMemory` at `0x18003af13`
- `ntdll!RtlAllocateHeap` at `0x18003aea8`
- `ntdll!RtlAllocateHeap` at `0x18003aea8`
- `ntdll!RtlFreeHeap` at `0x18003aff2`
- `ntdll!RtlFreeHeap` at `0x18003b010`
- `ntdll!RtlFreeHeap` at `0x18003aff2`
- `ntdll!RtlFreeHeap` at `0x18003b010`
- `ADVAPI32!RegQueryValueExW` at `0x18003ae6f`
- `ADVAPI32!RegQueryValueExW` at `0x18003aefe`
- `ADVAPI32!RegQueryValueExW` at `0x18003ae6f`
- `ADVAPI32!RegQueryValueExW` at `0x18003aefe`
- `ADVAPI32!RegCloseKey` at `0x18003afcd`
- `ADVAPI32!RegCloseKey` at `0x18003afcd`
- `ADVAPI32!RegSetValueExW` at `0x18003af4b`
- `ADVAPI32!RegSetValueExW` at `0x18003af4b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003ae35`
- `ADVAPI32!RegCreateKeyExW` at `0x18003ae35`

## string_xrefs

- `0x18003aeb6`: `GenericSetRegBeforeUpgMigrationShim:Collect : Allocate memory for reading registry failed`
- `0x18003af6c`: `GenericSetRegBeforeUpgMigrationShim:Collect : Set registry Value Data failed, Value Name: %ws Error:[%x]`
- `0x18003af92`: `GenericSetRegBeforeUpgMigrationShim:Collect : Can not open Root Key  name: %ws Error:[%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GenericSetRegBeforeUpgMigrationShimCollect(
        int *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  BYTE *Heap; // rbx
  const WCHAR *v6; // rdx
  LSTATUS Key; // ecx
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rdx
  int v10; // eax
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  LPCWSTR *v13; // rcx
  LPCWSTR *v14; // rax
  REGSAM samDesired[2]; // [rsp+30h] [rbp-71h]
  REGSAM samDesireda[2]; // [rsp+30h] [rbp-71h]
  DWORD cbData; // [rsp+58h] [rbp-49h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-45h] BYREF
  HKEY phkResult[3]; // [rsp+60h] [rbp-41h] BYREF
  _BYTE v21[8]; // [rsp+78h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-21h]
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-19h] BYREF
  __m128i si128; // [rsp+98h] [rbp-9h]
  DWORD dwType; // [rsp+A8h] [rbp+7h]
  LPCWSTR lpValueName[2]; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+C0h] [rbp+1Fh]
  unsigned __int64 v28; // [rsp+C8h] [rbp+27h]
  SIZE_T Length; // [rsp+D0h] [rbp+2Fh]
  void *Source2; // [rsp+D8h] [rbp+37h]

  phkResult[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  phkResult[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  cbData = 0;
  Heap = 0;
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  *(_OWORD *)lpValueName = 0;
  v27 = 0;
  v28 = 7;
  LOWORD(lpValueName[0]) = 0;
  Source2 = 0;
  *a1 = 1;
  if ( (unsigned int)ParseCommandLine(a3, (struct _GenericSetRegBeforeUpgREG1 *)v21) )
  {
    if ( v21[0] != 2 )
    {
      v6 = (const WCHAR *)lpSubKey;
      if ( si128.m128i_i64[1] > 7uLL )
        v6 = lpSubKey[0];
      Key = RegCreateKeyExW(hKey, v6, 0, 0, 0, 0x20007u, 0, phkResult, 0);
      if ( Key )
      {
        v14 = lpSubKey;
        if ( si128.m128i_i64[1] > 7uLL )
          v14 = (LPCWSTR *)lpSubKey[0];
        samDesired[0] = Key;
        AslLogCallPrintf(
          1,
          "GenericSetRegBeforeUpgMigrationShimCollect",
          635,
          "GenericSetRegBeforeUpgMigrationShim:Collect : Can not open Root Key  name: %ws Error:[%x]",
          v14,
          *(_QWORD *)samDesired);
      }
      else
      {
        cbData = 0;
        v8 = (const WCHAR *)lpValueName;
        if ( v28 > 7 )
          v8 = lpValueName[0];
        if ( RegQueryValueExW(phkResult[0], v8, 0, &Type, 0, &cbData) || Type != dwType || cbData != (_DWORD)Length )
          goto LABEL_17;
        Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, cbData);
        if ( !Heap )
        {
          AslLogCallPrintf(
            1,
            "GenericSetRegBeforeUpgMigrationShimCollect",
            593,
            "GenericSetRegBeforeUpgMigrationShim:Collect : Allocate memory for reading registry failed");
          goto LABEL_28;
        }
        v9 = (const WCHAR *)lpValueName;
        if ( v28 > 7 )
          v9 = lpValueName[0];
        if ( RegQueryValueExW(phkResult[0], v9, 0, &Type, Heap, &cbData)
          || (v10 = RtlCompareMemory(Heap, Source2, (unsigned int)Length), v10 != (_DWORD)Length) )
        {
LABEL_17:
          v11 = (const WCHAR *)lpValueName;
          if ( v28 > 7 )
            v11 = lpValueName[0];
          v12 = RegSetValueExW(phkResult[0], v11, 0, dwType, (const BYTE *)Source2, Length);
          if ( v12 )
          {
            v13 = lpValueName;
            if ( v28 > 7 )
              v13 = (LPCWSTR *)lpValueName[0];
            samDesireda[0] = v12;
            AslLogCallPrintf(
              1,
              "GenericSetRegBeforeUpgMigrationShimCollect",
              626,
              "GenericSetRegBeforeUpgMigrationShim:Collect : Set registry Value Data failed, Value Name: %ws Error:[%x]",
              v13,
              *(_QWORD *)samDesireda);
          }
        }
      }
    }
    if ( (unsigned __int8)(v21[0] - 2) <= 1u )
      *a1 = 0;
  }
LABEL_28:
  if ( (unsigned __int64)phkResult[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult[0]);
    phkResult[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( Source2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Source2);
  std::wstring::~wstring(lpValueName);
  std::wstring::~wstring(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18003ad60  mov     rax, rsp
0x18003ad63  push    rbp
0x18003ad64  lea     rbp, [rax-5Fh]
0x18003ad68  sub     rsp, 0F0h
0x18003ad6f  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18003ad77  mov     [rax+10h], rbx
0x18003ad7b  mov     [rax+20h], rdi
0x18003ad7f  mov     rax, cs:__security_cookie
0x18003ad86  xor     rax, rsp
0x18003ad89  mov     [rbp+57h+var_10], rax
0x18003ad8d  mov     rdi, rcx
0x18003ad90  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x18003ad98  mov     [rbp+57h+Type], 0
0x18003ad9f  mov     [rbp+57h+cbData], 0
0x18003ada6  xor     ebx, ebx
0x18003ada8  xorps   xmm0, xmm0
0x18003adab  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18003adaf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003adb7  movdqa  [rbp+57h+var_60], xmm1
0x18003adbc  xor     eax, eax
0x18003adbe  mov     word ptr [rbp+57h+lpSubKey], ax
0x18003adc2  movups  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18003adc6  mov     [rbp+57h+var_38], rax
0x18003adca  mov     [rbp+57h+var_30], 7
0x18003add2  mov     word ptr [rbp+57h+lpValueName], ax
0x18003add6  mov     [rbp+57h+Source2], rax
0x18003adda  mov     dword ptr [rcx], 1
0x18003ade0  lea     rdx, [rbp+57h+var_80]; struct _GenericSetRegBeforeUpgREG1 *
0x18003ade4  mov     rcx, r8; unsigned __int16 *
0x18003ade7  call    ?ParseCommandLine@@YAHPEBGPEAU_GenericSetRegBeforeUpgREG1@@@Z; ParseCommandLine(ushort const *,_GenericSetRegBeforeUpgREG1 *)
0x18003adec  test    eax, eax
0x18003adee  jz      loc_18003AFBF
0x18003adf4  cmp     [rbp+57h+var_80], 2
0x18003adf8  jz      loc_18003AFB0
0x18003adfe  lea     rdx, [rbp+57h+lpSubKey]
0x18003ae02  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18003ae07  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003ae0c  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x18003ae11  lea     rax, [rbp+57h+var_98]
0x18003ae15  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003ae1a  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18003ae1f  mov     [rsp+0F0h+samDesired], 20007h; samDesired
0x18003ae27  mov     [rsp+0F0h+dwOptions], ebx; dwOptions
0x18003ae2b  xor     r9d, r9d; lpClass
0x18003ae2e  xor     r8d, r8d; Reserved
0x18003ae31  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ae35  call    cs:__imp_RegCreateKeyExW
0x18003ae3b  mov     ecx, eax
0x18003ae3d  test    eax, eax
0x18003ae3f  jnz     loc_18003AF7B
0x18003ae45  mov     [rbp+57h+cbData], eax
0x18003ae48  lea     rdx, [rbp+57h+lpValueName]
0x18003ae4c  cmp     [rbp+57h+var_30], 7
0x18003ae51  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18003ae56  lea     rax, [rbp+57h+cbData]
0x18003ae5a  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x18003ae5f  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x18003ae64  lea     r9, [rbp+57h+Type]; lpType
0x18003ae68  xor     r8d, r8d; lpReserved
0x18003ae6b  mov     rcx, [rbp+57h+var_98]; hKey
0x18003ae6f  call    cs:__imp_RegQueryValueExW
0x18003ae75  test    eax, eax
0x18003ae77  jnz     loc_18003AF22
0x18003ae7d  mov     eax, [rbp+57h+dwType]
0x18003ae80  cmp     [rbp+57h+Type], eax
0x18003ae83  jnz     loc_18003AF22
0x18003ae89  mov     eax, [rbp+57h+cbData]
0x18003ae8c  cmp     eax, dword ptr [rbp+57h+Length]
0x18003ae8f  jnz     loc_18003AF22
0x18003ae95  mov     r8d, eax; Size
0x18003ae98  mov     rcx, gs:60h
0x18003aea1  lea     edx, [rbx+8]; Flags
0x18003aea4  mov     rcx, [rcx+30h]; HeapHandle
0x18003aea8  call    cs:__imp_RtlAllocateHeap
0x18003aeae  mov     rbx, rax
0x18003aeb1  test    rax, rax
0x18003aeb4  jnz     short loc_18003AED7
0x18003aeb6  lea     r9, aGenericsetregb_7; "GenericSetRegBeforeUpgMigrationShim:Col"...
0x18003aebd  mov     r8d, 251h
0x18003aec3  lea     rdx, aGenericsetregb_4; "GenericSetRegBeforeUpgMigrationShimColl"...
0x18003aeca  lea     ecx, [rax+1]
0x18003aecd  call    AslLogCallPrintf
0x18003aed2  jmp     loc_18003AFBF
0x18003aed7  lea     rdx, [rbp+57h+lpValueName]
0x18003aedb  cmp     [rbp+57h+var_30], 7
0x18003aee0  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18003aee5  lea     rax, [rbp+57h+cbData]
0x18003aee9  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x18003aeee  mov     qword ptr [rsp+0F0h+dwOptions], rbx; lpData
0x18003aef3  lea     r9, [rbp+57h+Type]; lpType
0x18003aef7  xor     r8d, r8d; lpReserved
0x18003aefa  mov     rcx, [rbp+57h+var_98]; hKey
0x18003aefe  call    cs:__imp_RegQueryValueExW
0x18003af04  test    eax, eax
0x18003af06  jnz     short loc_18003AF22
0x18003af08  mov     r8d, dword ptr [rbp+57h+Length]; Length
0x18003af0c  mov     rdx, [rbp+57h+Source2]; Source2
0x18003af10  mov     rcx, rbx; Source1
0x18003af13  call    cs:__imp_RtlCompareMemory
0x18003af19  cmp     eax, dword ptr [rbp+57h+Length]
0x18003af1c  jz      loc_18003AFB0
0x18003af22  lea     rdx, [rbp+57h+lpValueName]
0x18003af26  cmp     [rbp+57h+var_30], 7
0x18003af2b  cmova   rdx, [rbp+57h+lpValueName]; lpValueName
0x18003af30  mov     eax, dword ptr [rbp+57h+Length]
0x18003af33  mov     [rsp+0F0h+samDesired], eax; cbData
0x18003af37  mov     rax, [rbp+57h+Source2]
0x18003af3b  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18003af40  mov     r9d, [rbp+57h+dwType]; dwType
0x18003af44  xor     r8d, r8d; Reserved
0x18003af47  mov     rcx, [rbp+57h+var_98]; hKey
0x18003af4b  call    cs:__imp_RegSetValueExW
0x18003af51  test    eax, eax
0x18003af53  jz      short loc_18003AFB0
0x18003af55  lea     rcx, [rbp+57h+lpValueName]
0x18003af59  cmp     [rbp+57h+var_30], 7
0x18003af5e  cmova   rcx, [rbp+57h+lpValueName]
0x18003af63  mov     [rsp+0F0h+samDesired], eax
0x18003af67  mov     qword ptr [rsp+0F0h+dwOptions], rcx
0x18003af6c  lea     r9, aGenericsetregb_9; "GenericSetRegBeforeUpgMigrationShim:Col"...
0x18003af73  mov     r8d, 272h
0x18003af79  jmp     short loc_18003AF9F
0x18003af7b  lea     rax, [rbp+57h+lpSubKey]
0x18003af7f  cmp     qword ptr [rbp+57h+var_60+8], 7
0x18003af84  cmova   rax, [rbp+57h+lpSubKey]
0x18003af89  mov     [rsp+0F0h+samDesired], ecx
0x18003af8d  mov     qword ptr [rsp+0F0h+dwOptions], rax
0x18003af92  lea     r9, aGenericsetregb_5; "GenericSetRegBeforeUpgMigrationShim:Col"...
0x18003af99  mov     r8d, 27Bh
0x18003af9f  lea     rdx, aGenericsetregb_4; "GenericSetRegBeforeUpgMigrationShimColl"...
0x18003afa6  mov     ecx, 1
0x18003afab  call    AslLogCallPrintf
0x18003afb0  mov     al, [rbp+57h+var_80]
0x18003afb3  sub     al, 2
0x18003afb5  cmp     al, 1
0x18003afb7  ja      short loc_18003AFBF
0x18003afb9  mov     dword ptr [rdi], 0
0x18003afbf  mov     rcx, [rbp+57h+var_98]; hKey
0x18003afc3  lea     rax, [rcx-1]
0x18003afc7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003afcb  ja      short loc_18003AFDB
0x18003afcd  call    cs:__imp_RegCloseKey
0x18003afd3  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x18003afdb  test    rbx, rbx
0x18003afde  jz      short loc_18003AFF8
0x18003afe0  mov     rcx, gs:60h
0x18003afe9  mov     r8, rbx; P
0x18003afec  xor     edx, edx; Flags
0x18003afee  mov     rcx, [rcx+30h]; HeapHandle
0x18003aff2  call    cs:__imp_RtlFreeHeap
0x18003aff8  mov     r8, [rbp+57h+Source2]; P
0x18003affc  test    r8, r8
0x18003afff  jz      short loc_18003B017
0x18003b001  mov     rcx, gs:60h
0x18003b00a  xor     edx, edx; Flags
0x18003b00c  mov     rcx, [rcx+30h]; HeapHandle
0x18003b010  call    cs:__imp_RtlFreeHeap
0x18003b016  nop
0x18003b017  lea     rcx, [rbp+57h+lpValueName]; void *
0x18003b01b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b020  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18003b024  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b029  xor     eax, eax
0x18003b02b  mov     rcx, [rbp+57h+var_10]
0x18003b02f  xor     rcx, rsp; StackCookie
0x18003b032  call    __security_check_cookie
0x18003b037  lea     r11, [rsp+0F0h+var_s0]
0x18003b03f  mov     rbx, [r11+18h]
0x18003b043  mov     rdi, [r11+28h]
0x18003b047  mov     rsp, r11
0x18003b04a  pop     rbp
0x18003b04b  retn
```
