# UfhpUtilityStoreData(_UFH_DATA_TYPE,ushort const *,ushort const *,ushort const *)

- ea: `0x180035458`
- end: `0x180035644`
- name: `?UfhpUtilityStoreData@@YAKW4_UFH_DATA_TYPE@@PEBG11@Z`
- size: `492`
- prototype: `unsigned int __high(enum _UFH_DATA_TYPE, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180039500`
- `0x1800b2fa4`

## callees

- `0x180035458`
- `0x180035738`
- `0x18003ba5c`
- `0x18007a9cf`
- `0x1800f13f8`
- `0x1800f14f8`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_itow_s` at `0x180035570`
- `msvcrt!_itow_s` at `0x180035570`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800355db`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800355db`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800355ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800355ee`
- `ntdll!RtlFreeHeap` at `0x18003561b`
- `ntdll!RtlFreeHeap` at `0x18003561b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003551e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003551e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800354e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800354e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800355c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800355c6`

## pseudocode

```c
__int64 __fastcall UfhpUtilityStoreData(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  BYTE *v7; // rdi
  const WCHAR *StorePath; // rsi
  unsigned int TopValue; // ebx
  int v10; // esi
  unsigned int AllocMultiSz; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int Value; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v17; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  memset_0(Buffer, 0, 0x208u);
  v7 = 0;
  Value = 0;
  lpData = 0;
  v17 = 0;
  StorePath = (const WCHAR *)UfhpUtilityGetStorePath(0);
  TopValue = RegOpenKeyExW(HKEY_LOCAL_MACHINE, StorePath, 0, 0xF003Fu, &hKey);
  if ( TopValue == 2 )
    TopValue = RegCreateKeyExW(HKEY_LOCAL_MACHINE, StorePath, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !TopValue )
  {
    TopValue = UfhpUtilityStoreDeleteAboveQuota(hKey);
    if ( !TopValue )
    {
      TopValue = UfhpGetTopValue(&Value, hKey);
      if ( !TopValue )
      {
        v10 = Value;
        if ( _itow_s(Value, Buffer, 0x104u, 10) )
        {
          TopValue = 1359;
        }
        else
        {
          AllocMultiSz = UfhpUtilityGetAllocMultiSz((unsigned __int16 **)&lpData, &v17, a2, a3, a4);
          v7 = lpData;
          TopValue = AllocMultiSz;
          if ( !AllocMultiSz )
          {
            TopValue = RegSetValueExW(hKey, Buffer, 0, 7u, lpData, 2 * v17);
            if ( !TopValue )
            {
              RtlAcquireSRWLockExclusive(&qword_18015C498, v12, v13);
              dword_18015C48C = v10 + 1;
              RtlReleaseSRWLockExclusive(&qword_18015C498);
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return TopValue;
}

```

## disassembly

```asm
0x180035458  push    rbp
0x18003545a  push    rbx
0x18003545b  push    rsi
0x18003545c  push    rdi
0x18003545d  push    r12
0x18003545f  push    r14
0x180035461  push    r15
0x180035463  lea     rbp, [rsp-190h]
0x18003546b  sub     rsp, 290h
0x180035472  mov     rax, cs:__security_cookie
0x180035479  xor     rax, rsp
0x18003547c  mov     [rbp+1C0h+var_40], rax
0x180035483  mov     r15, r8
0x180035486  mov     [rsp+2C0h+hKey], 0
0x18003548f  mov     r14, rdx
0x180035492  lea     rcx, [rsp+2C0h+Buffer]; void *
0x180035497  xor     edx, edx; Val
0x180035499  mov     r8d, 208h; Size
0x18003549f  mov     r12, r9
0x1800354a2  call    memset_0
0x1800354a7  xor     edi, edi
0x1800354a9  mov     [rsp+2C0h+Value], 0
0x1800354b1  xor     ecx, ecx
0x1800354b3  mov     [rsp+2C0h+lpData], rdi
0x1800354b8  mov     [rsp+2C0h+var_264], edi
0x1800354bc  call    ?UfhpUtilityGetStorePath@@YAPEAGW4_UFH_DATA_TYPE@@@Z; UfhpUtilityGetStorePath(_UFH_DATA_TYPE)
0x1800354c1  mov     rsi, rax
0x1800354c4  mov     r9d, 0F003Fh; samDesired
0x1800354ca  lea     rax, [rsp+2C0h+hKey]
0x1800354cf  mov     rdx, rsi; lpSubKey
0x1800354d2  xor     r8d, r8d; ulOptions
0x1800354d5  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800354da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800354e1  call    cs:__imp_RegOpenKeyExW
0x1800354e7  mov     ebx, eax
0x1800354e9  cmp     eax, 2
0x1800354ec  jnz     short loc_180035526
0x1800354ee  mov     [rsp+2C0h+lpdwDisposition], rdi; lpdwDisposition
0x1800354f3  lea     rax, [rsp+2C0h+hKey]
0x1800354f8  mov     [rsp+2C0h+var_288], rax; phkResult
0x1800354fd  xor     r9d, r9d; lpClass
0x180035500  mov     [rsp+2C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180035505  xor     r8d, r8d; Reserved
0x180035508  mov     [rsp+2C0h+samDesired], 0F003Fh; samDesired
0x180035510  mov     rdx, rsi; lpSubKey
0x180035513  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003551a  mov     dword ptr [rsp+2C0h+phkResult], edi; dwOptions
0x18003551e  call    cs:__imp_RegCreateKeyExW
0x180035524  mov     ebx, eax
0x180035526  test    ebx, ebx
0x180035528  jnz     loc_1800355F4
0x18003552e  mov     rcx, [rsp+2C0h+hKey]
0x180035533  call    ?UfhpUtilityStoreDeleteAboveQuota@@YAKPEAUHKEY__@@W4_UFH_DATA_TYPE@@@Z; UfhpUtilityStoreDeleteAboveQuota(HKEY__ *,_UFH_DATA_TYPE)
0x180035538  mov     ebx, eax
0x18003553a  test    eax, eax
0x18003553c  jnz     loc_1800355F4
0x180035542  mov     rdx, [rsp+2C0h+hKey]
0x180035547  lea     rcx, [rsp+2C0h+Value]
0x18003554c  call    ?UfhpGetTopValue@@YAKPEAKPEAUHKEY__@@W4_UFH_DATA_TYPE@@@Z; UfhpGetTopValue(ulong *,HKEY__ *,_UFH_DATA_TYPE)
0x180035551  mov     ebx, eax
0x180035553  test    eax, eax
0x180035555  jnz     loc_1800355F4
0x18003555b  mov     esi, [rsp+2C0h+Value]
0x18003555f  lea     r9d, [rax+0Ah]; Radix
0x180035563  mov     ecx, esi; Value
0x180035565  lea     rdx, [rsp+2C0h+Buffer]; Buffer
0x18003556a  mov     r8d, 104h; BufferCount
0x180035570  call    cs:__imp__itow_s
0x180035576  test    eax, eax
0x180035578  jz      short loc_180035581
0x18003557a  mov     ebx, 54Fh
0x18003557f  jmp     short loc_1800355F4
0x180035581  mov     r9, r15; unsigned __int16 *
0x180035584  mov     [rsp+2C0h+phkResult], r12; unsigned __int16 *
0x180035589  mov     r8, r14; unsigned __int16 *
0x18003558c  lea     rdx, [rsp+2C0h+var_264]; unsigned int *
0x180035591  lea     rcx, [rsp+2C0h+lpData]; unsigned __int16 **
0x180035596  call    ?UfhpUtilityGetAllocMultiSz@@YAKPEAPEAGPEAKPEBG22@Z; UfhpUtilityGetAllocMultiSz(ushort * *,ulong *,ushort const *,ushort const *,ushort const *)
0x18003559b  mov     rdi, [rsp+2C0h+lpData]
0x1800355a0  mov     ebx, eax
0x1800355a2  test    eax, eax
0x1800355a4  jnz     short loc_1800355F4
0x1800355a6  mov     eax, [rsp+2C0h+var_264]
0x1800355aa  lea     r9d, [rbx+7]; dwType
0x1800355ae  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800355b3  lea     rdx, [rsp+2C0h+Buffer]; lpValueName
0x1800355b8  add     eax, eax
0x1800355ba  xor     r8d, r8d; Reserved
0x1800355bd  mov     [rsp+2C0h+samDesired], eax; cbData
0x1800355c1  mov     [rsp+2C0h+phkResult], rdi; lpData
0x1800355c6  call    cs:__imp_RegSetValueExW
0x1800355cc  mov     ebx, eax
0x1800355ce  test    eax, eax
0x1800355d0  jnz     short loc_1800355F4
0x1800355d2  lea     rcx, qword_18015C498
0x1800355d9  inc     esi
0x1800355db  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800355e1  lea     rcx, qword_18015C498
0x1800355e8  mov     cs:dword_18015C48C, esi
0x1800355ee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800355f4  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800355f9  test    rcx, rcx
0x1800355fc  jz      short loc_180035604
0x1800355fe  call    cs:__imp_RegCloseKey
0x180035604  test    rdi, rdi
0x180035607  jz      short loc_180035621
0x180035609  mov     rcx, gs:60h
0x180035612  mov     r8, rdi; P
0x180035615  xor     edx, edx; Flags
0x180035617  mov     rcx, [rcx+30h]; HeapHandle
0x18003561b  call    cs:__imp_RtlFreeHeap
0x180035621  mov     eax, ebx
0x180035623  mov     rcx, [rbp+1C0h+var_40]
0x18003562a  xor     rcx, rsp; StackCookie
0x18003562d  call    __security_check_cookie
0x180035632  add     rsp, 290h
0x180035639  pop     r15
0x18003563b  pop     r14
0x18003563d  pop     r12
0x18003563f  pop     rdi
0x180035640  pop     rsi
0x180035641  pop     rbx
0x180035642  pop     rbp
0x180035643  retn
```
