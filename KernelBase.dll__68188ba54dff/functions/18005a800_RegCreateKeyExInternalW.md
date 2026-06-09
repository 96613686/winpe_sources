# RegCreateKeyExInternalW

- ea: `0x18005a800`
- end: `0x18005add2`
- name: `RegCreateKeyExInternalW`
- size: `1490`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f558`
- `0x180051660`
- `0x180053f44`
- `0x1800594f0`
- `0x180093d60`
- `0x1800945b4`
- `0x180094fc0`
- `0x1800962c4`
- `0x1800963c0`
- `0x18009858c`
- `0x1800da32c`
- `0x1800fee00`
- `0x1801013b4`
- `0x18010b6a8`
- `0x18010bed4`
- `0x180121968`
- `0x180129b60`
- `0x1801334e0`
- `0x180142208`
- `0x18014258c`
- `0x1801437e8`
- `0x18016c540`

## callees

- `0x18005a0c0`
- `0x18005a800`
- `0x18005b460`
- `0x18005bb80`
- `0x18005d2c0`
- `0x1800a6e58`
- `0x18012d578`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18005a9e1`
- `ntdll!RtlEnterCriticalSection` at `0x18005a9e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005aa14`
- `ntdll!RtlLeaveCriticalSection` at `0x18005aa14`
- `ntdll!RtlNtStatusToDosError` at `0x18005abcb`
- `ntdll!RtlNtStatusToDosError` at `0x18005ac8d`
- `ntdll!RtlNtStatusToDosError` at `0x18005adb4`
- `ntdll!RtlNtStatusToDosError` at `0x18005adc4`
- `ntdll!RtlNtStatusToDosError` at `0x18005abcb`
- `ntdll!RtlNtStatusToDosError` at `0x18005ac8d`
- `ntdll!RtlNtStatusToDosError` at `0x18005adb4`
- `ntdll!RtlNtStatusToDosError` at `0x18005adc4`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005a9cf`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005a9cf`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005a8b6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ac0f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005a8b6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ac0f`
- `ntdll!NtClose` at `0x18005aa1f`
- `ntdll!NtClose` at `0x18005aa1f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005aa9b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005aa9b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005aacc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005aacc`
- `ntdll!RtlValidSecurityDescriptor` at `0x18005ab51`
- `ntdll!RtlValidSecurityDescriptor` at `0x18005ab51`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005ab62`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18005ab62`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18005abc3`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18005abc3`
- `ntdll!RtlFreeHeap` at `0x18005a971`
- `ntdll!RtlFreeHeap` at `0x18005aa89`
- `ntdll!RtlFreeHeap` at `0x18005aaf5`
- `ntdll!RtlFreeHeap` at `0x18005a971`
- `ntdll!RtlFreeHeap` at `0x18005aa89`
- `ntdll!RtlFreeHeap` at `0x18005aaf5`
- `ntdll!RtlAllocateHeap` at `0x18005ab8e`
- `ntdll!RtlAllocateHeap` at `0x18005ab8e`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005ad77`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005ad77`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ac42`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005ac42`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18005ad09`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18005ad09`

## pseudocode

```c
__int64 __fastcall RegCreateKeyExInternalW(
        HKEY a1,
        const WCHAR *a2,
        int a3,
        const WCHAR *a4,
        ULONG a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  HKEY *v12; // rsi
  HANDLE *v13; // r14
  unsigned int v14; // r12d
  int inited; // eax
  __int64 v16; // rcx
  __int64 v17; // rbx
  PVOID *v18; // rbx
  unsigned __int64 v19; // rdi
  HKEY v20; // rcx
  LPWCH v21; // r15
  HANDLE v22; // r14
  _QWORD *v23; // rcx
  _QWORD *v24; // rdi
  _QWORD *i; // rbx
  int v26; // eax
  _QWORD *v28; // rax
  __int64 v29; // r8
  _QWORD *v31; // rax
  WCHAR *v32; // rcx
  _QWORD *v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rax
  void *v36; // rdi
  ULONG v37; // r15d
  PVOID Heap; // rax
  NTSTATUS SelfRelativeSD; // eax
  __int64 v40; // rcx
  unsigned __int64 v41; // rdi
  bool v42; // dl
  unsigned int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // r9
  int v46; // [rsp+30h] [rbp-B8h]
  HANDLE Handle; // [rsp+58h] [rbp-90h] BYREF
  HKEY v48; // [rsp+60h] [rbp-88h] BYREF
  LPWCH v49; // [rsp+68h] [rbp-80h] BYREF
  struct _UNICODE_STRING v50; // [rsp+70h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-68h] BYREF
  _QWORD v52[11]; // [rsp+90h] [rbp-58h] BYREF
  HANDLE KeyHandle; // [rsp+F0h] [rbp+8h] BYREF

  KeyHandle = a1;
  DestinationString = 0;
  v50 = 0;
  memset(v52, 0, 28);
  v12 = 0;
  v48 = 0;
  v49 = 0;
  if ( a1 == HKEY_PERFORMANCE_DATA || a1 == HKEY_PERFORMANCE_TEXT || a1 == HKEY_PERFORMANCE_NLSTEXT )
    return 6;
  if ( a3 )
    return 87;
  if ( !a2 )
    return 1010;
  v13 = (HANDLE *)a8;
  if ( !a8 )
    return 1010;
  v14 = MapPredefinedHandleInternal(a1, (HKEY *)&KeyHandle, &v48, &v49);
  if ( v14 )
    goto LABEL_17;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( inited < 0 )
    goto LABEL_81;
  DestinationString.Length += 2;
  if ( !a4 )
  {
    *(_DWORD *)&v50.Length = 0;
    v50.Buffer = 0;
    goto LABEL_11;
  }
  inited = RtlInitUnicodeStringEx(&v50, a4);
  if ( inited < 0 )
  {
LABEL_81:
    v14 = RtlNtStatusToDosError(inited);
    goto LABEL_17;
  }
  v50.Length += 2;
LABEL_11:
  v17 = a7;
  if ( !a7 )
  {
    v18 = 0;
LABEL_13:
    Handle = v18;
    v19 = (unsigned __int64)KeyHandle;
    if ( ((unsigned __int8)KeyHandle & 1) != 0 )
    {
      if ( (unsigned __int8)IsBaseRegCloseKeyPresent(v16) )
      {
        LODWORD(KeyHandle) = 0;
        v41 = v19 & 0xFFFFFFFFFFFFFFFEuLL;
        v42 = (unsigned __int8)IsBaseRegCloseKeyPresent(v40)
           && !(unsigned int)BaseRegGetVersion(v41, &KeyHandle)
           && (_DWORD)KeyHandle == 6;
        v43 = a6 & 0xFFFFFCFF;
        if ( v42 )
          v43 = a6;
        v14 = BaseRegCreateKey(v41, &DestinationString, &v50, a5, v43, v18, v13, a9);
        if ( !v14 )
          *v13 = (HANDLE)((unsigned __int64)*v13 | 1);
      }
    }
    else
    {
      v14 = BaseRegCreateKeyInternal(
              KeyHandle,
              &DestinationString,
              &v50,
              a5,
              a6,
              (__int64)v18,
              v46,
              v13,
              (_DWORD *)a9,
              (void *)a10);
    }
    if ( v18 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18[1]);
    goto LABEL_17;
  }
  v52[1] = 0;
  v36 = *(void **)(a7 + 8);
  if ( !v36 )
  {
    v52[2] = 0;
    v14 = 0;
    goto LABEL_56;
  }
  if ( RtlValidSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a7 + 8)) )
  {
    v37 = RtlLengthSecurityDescriptor(v36);
    Heap = (PVOID)v52[1];
    if ( v52[1] )
    {
      if ( LODWORD(v52[2]) >= v37 )
        goto LABEL_54;
      v14 = 14;
    }
    else
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
      v52[1] = Heap;
      if ( Heap )
      {
        LODWORD(v52[2]) = v37;
LABEL_54:
        HIDWORD(v52[2]) = v37;
        SelfRelativeSD = RtlMakeSelfRelativeSD(v36, Heap, (PULONG)&v52[2]);
        v14 = RtlNtStatusToDosError(SelfRelativeSD);
        goto LABEL_55;
      }
      v14 = 14;
    }
  }
  else
  {
    v14 = 87;
  }
LABEL_55:
  if ( !v14 )
  {
LABEL_56:
    LODWORD(v52[0]) = *(_DWORD *)v17;
    LOBYTE(v52[3]) = *(_BYTE *)(v17 + 16);
    v18 = (PVOID *)v52;
    goto LABEL_13;
  }
LABEL_17:
  v20 = v48;
  Handle = v48;
  v21 = v49;
  if ( v48 )
  {
    if ( v48 == HKEY_PERFORMANCE_DATA || v48 == HKEY_PERFORMANCE_TEXT || v48 == HKEY_PERFORMANCE_NLSTEXT )
    {
      if ( (unsigned __int8)IsBaseRegCloseKeyPresent(v48) )
        PerfRegCloseKey(&Handle);
    }
    else
    {
      if ( ((unsigned __int8)v48 & 2) != 0 )
      {
        RtlRunOnceExecuteOnce(&gClassesEnumTableInit, ClassesEnumTableInitFn, 0, 0);
        v22 = Handle;
        RtlEnterCriticalSection(&CriticalSection);
        v23 = (_QWORD *)qword_18039F308;
        if ( qword_18039F308 )
        {
          do
          {
            v24 = (_QWORD *)*v23;
            for ( i = (_QWORD *)v23[3]; i; i = (_QWORD *)*i )
            {
              if ( v22 == (HANDLE)i[2] )
              {
                if ( i != (_QWORD *)v23[3] )
                {
                  v33 = (_QWORD *)i[1];
                  v34 = (_QWORD *)*i;
                  if ( v33 )
                    *v33 = v34;
                  if ( v34 )
                    v34[1] = v33;
                  v35 = v23[3];
                  if ( v35 )
                  {
                    *i = v35;
                    *(_QWORD *)(v23[3] + 8LL) = i;
                  }
                  v23[3] = i;
                  i[1] = 0;
                }
                v28 = (_QWORD *)*i;
                v23[3] = *i;
                if ( v28 )
                  v28[1] = 0;
                EnumStateClear(i);
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, i);
                break;
              }
            }
            v23 = v24;
          }
          while ( v24 );
        }
        RtlLeaveCriticalSection(&CriticalSection);
        v20 = (HKEY)Handle;
      }
      v26 = NtClose(v20);
      if ( v26 < 0 )
        RtlNtStatusToDosError(v26);
      else
        Handle = 0;
    }
  }
  if ( v21 )
  {
    RtlAcquireSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( (*((_DWORD *)v21 + 2))-- == 1 )
    {
      v31 = (_QWORD *)*((_QWORD *)v21 + 2);
      v32 = (WCHAR *)v31[1];
      if ( v21 != v32 || *(_QWORD *)v21 != *v31 )
      {
        v12 = (HKEY *)v21;
        v44 = RemoveUnitFromList(v32, v21, v29);
        *(_QWORD *)(v45 + 8) = v44;
      }
    }
    RtlReleaseSRWLockExclusive(PredefinedHandleTableSRWLock);
    if ( v12 )
    {
      RegCloseKey(*v12);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18005a800  mov     r11, rsp
0x18005a803  mov     [r11+8], rcx
0x18005a807  push    rbx
0x18005a808  push    rsi
0x18005a809  push    rdi
0x18005a80a  push    r12
0x18005a80c  push    r14
0x18005a80e  push    r15
0x18005a810  sub     rsp, 0B8h
0x18005a817  mov     rdi, r9
0x18005a81a  mov     rbx, rdx
0x18005a81d  xorps   xmm0, xmm0
0x18005a820  movups  xmmword ptr [r11-68h], xmm0
0x18005a825  xorps   xmm1, xmm1
0x18005a828  movups  xmmword ptr [rsp+0E8h+var_78.Length], xmm1
0x18005a82d  xor     eax, eax
0x18005a82f  movups  xmmword ptr [r11-58h], xmm0
0x18005a834  movups  xmmword ptr [r11-4Ch], xmm0
0x18005a839  xor     esi, esi
0x18005a83b  mov     [rsp+0E8h+var_88], rsi
0x18005a840  mov     [r11-80h], rsi
0x18005a844  cmp     rcx, 0FFFFFFFF80000004h
0x18005a84b  jz      loc_18005AC81
0x18005a851  cmp     rcx, 0FFFFFFFF80000050h
0x18005a858  jz      loc_18005AC81
0x18005a85e  cmp     rcx, 0FFFFFFFF80000060h
0x18005a865  jz      loc_18005AC81
0x18005a86b  test    r8d, r8d
0x18005a86e  jnz     loc_18005AD40
0x18005a874  test    rdx, rdx
0x18005a877  jz      loc_18005AD56
0x18005a87d  mov     r14, [rsp+0E8h+arg_38]
0x18005a885  test    r14, r14
0x18005a888  jz      loc_18005AD56
0x18005a88e  lea     r9, [r11-80h]
0x18005a892  lea     r8, [rsp+0E8h+var_88]
0x18005a897  lea     rdx, [r11+8]
0x18005a89b  call    MapPredefinedHandleInternal
0x18005a8a0  mov     r12d, eax
0x18005a8a3  test    eax, eax
0x18005a8a5  jnz     loc_18005A977
0x18005a8ab  mov     rdx, rbx; SourceString
0x18005a8ae  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18005a8b6  call    cs:__imp_RtlInitUnicodeStringEx
0x18005a8bc  test    eax, eax
0x18005a8be  js      loc_18005ADC2
0x18005a8c4  add     [rsp+0E8h+DestinationString.Length], 2
0x18005a8cd  test    rdi, rdi
0x18005a8d0  jnz     loc_18005AC07
0x18005a8d6  mov     dword ptr [rsp+0E8h+var_78.Length], esi
0x18005a8da  mov     [rsp+0E8h+var_78.Buffer], rsi
0x18005a8df  mov     rbx, [rsp+0E8h+arg_30]
0x18005a8e7  test    rbx, rbx
0x18005a8ea  jnz     loc_18005AB39
0x18005a8f0  mov     rbx, rsi
0x18005a8f3  mov     [rsp+0E8h+Handle], rbx
0x18005a8f8  mov     rdi, [rsp+0E8h+KeyHandle]
0x18005a900  test    dil, 1
0x18005a904  jnz     loc_18005AC98
0x18005a90a  mov     rax, [rsp+0E8h+arg_48]
0x18005a912  mov     [rsp+0E8h+var_A0], rax; __int64
0x18005a917  mov     rax, [rsp+0E8h+arg_40]
0x18005a91f  mov     [rsp+0E8h+var_A8], rax; __int64
0x18005a924  mov     [rsp+0E8h+var_B0], r14; __int64
0x18005a929  mov     [rsp+0E8h+var_C0], rbx; __int64
0x18005a92e  mov     eax, [rsp+0E8h+arg_28]
0x18005a935  mov     [rsp+0E8h+var_C8], eax; int
0x18005a939  mov     r9d, [rsp+0E8h+arg_20]
0x18005a941  lea     r8, [rsp+0E8h+var_78]
0x18005a946  lea     rdx, [rsp+0E8h+DestinationString]; Source
0x18005a94e  mov     rcx, rdi; KeyHandle
0x18005a951  call    BaseRegCreateKeyInternal
0x18005a956  mov     r12d, eax
0x18005a959  test    rbx, rbx
0x18005a95c  jz      short loc_18005A977
0x18005a95e  mov     rcx, gs:60h
0x18005a967  mov     r8, [rbx+8]; P
0x18005a96b  xor     edx, edx; Flags
0x18005a96d  mov     rcx, [rcx+30h]; HeapHandle
0x18005a971  call    cs:__imp_RtlFreeHeap
0x18005a977  mov     rcx, [rsp+0E8h+var_88]
0x18005a97c  mov     [rsp+0E8h+Handle], rcx
0x18005a981  mov     r15, [rsp+0E8h+var_80]
0x18005a986  test    rcx, rcx
0x18005a989  jz      loc_18005AA32
0x18005a98f  cmp     rcx, 0FFFFFFFF80000004h
0x18005a996  jz      loc_18005AC30
0x18005a99c  cmp     rcx, 0FFFFFFFF80000050h
0x18005a9a3  jz      loc_18005AC30
0x18005a9a9  cmp     rcx, 0FFFFFFFF80000060h
0x18005a9b0  jz      loc_18005AC30
0x18005a9b6  test    cl, 2
0x18005a9b9  jz      short loc_18005AA1F
0x18005a9bb  xor     r9d, r9d
0x18005a9be  xor     r8d, r8d
0x18005a9c1  lea     rdx, ClassesEnumTableInitFn
0x18005a9c8  lea     rcx, gClassesEnumTableInit
0x18005a9cf  call    cs:__imp_RtlRunOnceExecuteOnce
0x18005a9d5  mov     r14, [rsp+0E8h+Handle]
0x18005a9da  lea     rcx, CriticalSection; CriticalSection
0x18005a9e1  call    cs:__imp_RtlEnterCriticalSection
0x18005a9e7  mov     rcx, cs:qword_18039F308
0x18005a9ee  test    rcx, rcx
0x18005a9f1  jz      short loc_18005AA0D
0x18005a9f3  mov     rdi, [rcx]
0x18005a9f6  mov     rax, [rcx+18h]
0x18005a9fa  mov     rbx, rax
0x18005a9fd  nop     dword ptr [rax]
0x18005aa00  test    rbx, rbx
0x18005aa03  jnz     short loc_18005AA4B
0x18005aa05  mov     rcx, rdi
0x18005aa08  test    rdi, rdi
0x18005aa0b  jnz     short loc_18005A9F3
0x18005aa0d  lea     rcx, CriticalSection; CriticalSection
0x18005aa14  call    cs:__imp_RtlLeaveCriticalSection
0x18005aa1a  mov     rcx, [rsp+0E8h+Handle]; Handle
0x18005aa1f  call    cs:__imp_NtClose
0x18005aa25  test    eax, eax
0x18005aa27  js      loc_18005AC8B
0x18005aa2d  mov     [rsp+0E8h+Handle], rsi
0x18005aa32  test    r15, r15
0x18005aa35  jnz     short loc_18005AA94
0x18005aa37  mov     eax, r12d
0x18005aa3a  add     rsp, 0B8h
0x18005aa41  pop     r15
0x18005aa43  pop     r14
0x18005aa45  pop     r12
0x18005aa47  pop     rdi
0x18005aa48  pop     rsi
0x18005aa49  pop     rbx
0x18005aa4a  retn
0x18005aa4b  cmp     r14, [rbx+10h]
0x18005aa4f  jz      short loc_18005AA56
0x18005aa51  mov     rbx, [rbx]
0x18005aa54  jmp     short loc_18005AA00
0x18005aa56  cmp     rbx, rax
0x18005aa59  jnz     loc_18005AB00
0x18005aa5f  mov     rax, [rbx]
0x18005aa62  mov     [rcx+18h], rax
0x18005aa66  test    rax, rax
0x18005aa69  jz      short loc_18005AA6F
0x18005aa6b  mov     [rax+8], rsi
0x18005aa6f  mov     rcx, rbx; void *
0x18005aa72  call    EnumStateClear
0x18005aa77  mov     rcx, gs:60h
0x18005aa80  mov     r8, rbx; P
0x18005aa83  xor     edx, edx; Flags
0x18005aa85  mov     rcx, [rcx+30h]; HeapHandle
0x18005aa89  call    cs:__imp_RtlFreeHeap
0x18005aa8f  jmp     loc_18005AA05
0x18005aa94  lea     rcx, PredefinedHandleTableSRWLock
0x18005aa9b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005aaa1  add     dword ptr [r15+8], 0FFFFFFFFh
0x18005aaa6  jnz     short loc_18005AAC5
0x18005aaa8  mov     rax, [r15+10h]
0x18005aaac  mov     rcx, [rax+8]
0x18005aab0  cmp     r15, rcx
0x18005aab3  jnz     loc_18005AD9A
0x18005aab9  mov     rax, [rax]
0x18005aabc  cmp     [r15], rax
0x18005aabf  jnz     loc_18005AD9A
0x18005aac5  lea     rcx, PredefinedHandleTableSRWLock
0x18005aacc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005aad2  test    rsi, rsi
0x18005aad5  jz      loc_18005AA37
0x18005aadb  mov     rcx, [rsi]; hKey
0x18005aade  call    RegCloseKey
0x18005aae3  mov     rcx, gs:60h
0x18005aaec  mov     r8, rsi; P
0x18005aaef  xor     edx, edx; Flags
0x18005aaf1  mov     rcx, [rcx+30h]; HeapHandle
0x18005aaf5  call    cs:__imp_RtlFreeHeap
0x18005aafb  jmp     loc_18005AA37
0x18005ab00  mov     rdx, [rbx+8]
0x18005ab04  mov     rax, [rbx]
0x18005ab07  test    rdx, rdx
0x18005ab0a  jz      short loc_18005AB0F
0x18005ab0c  mov     [rdx], rax
0x18005ab0f  test    rax, rax
0x18005ab12  jz      short loc_18005AB18
0x18005ab14  mov     [rax+8], rdx
0x18005ab18  mov     rax, [rcx+18h]
0x18005ab1c  test    rax, rax
0x18005ab1f  jz      short loc_18005AB2C
0x18005ab21  mov     [rbx], rax
0x18005ab24  mov     rax, [rcx+18h]
0x18005ab28  mov     [rax+8], rbx
0x18005ab2c  mov     [rcx+18h], rbx
0x18005ab30  mov     [rbx+8], rsi
0x18005ab34  jmp     loc_18005AA5F
0x18005ab39  mov     [rsp+0E8h+var_50], rsi
0x18005ab41  mov     rdi, [rbx+8]
0x18005ab45  test    rdi, rdi
0x18005ab48  jz      loc_18005AC66
0x18005ab4e  mov     rcx, rdi; SecurityDescriptor
0x18005ab51  call    cs:__imp_RtlValidSecurityDescriptor
0x18005ab57  test    al, al
0x18005ab59  jz      loc_18005AC28
0x18005ab5f  mov     rcx, rdi; SecurityDescriptor
0x18005ab62  call    cs:__imp_RtlLengthSecurityDescriptor
0x18005ab68  mov     r15d, eax
0x18005ab6b  mov     rax, [rsp+0E8h+var_50]
0x18005ab73  test    rax, rax
0x18005ab76  jnz     loc_18005AC4D
0x18005ab7c  mov     r8d, r15d; Size
0x18005ab7f  mov     rcx, gs:60h
0x18005ab88  xor     edx, edx; Flags
0x18005ab8a  mov     rcx, [rcx+30h]; HeapHandle
0x18005ab8e  call    cs:__imp_RtlAllocateHeap
0x18005ab94  mov     [rsp+0E8h+var_50], rax
0x18005ab9c  test    rax, rax
0x18005ab9f  jz      loc_18005AC76
0x18005aba5  mov     [rsp+0E8h+BufferLength], r15d
0x18005abad  mov     [rsp+0E8h+BufferLength+4], r15d
0x18005abb5  lea     r8, [rsp+0E8h+BufferLength]; BufferLength
0x18005abbd  mov     rdx, rax; SelfRelativeSD
0x18005abc0  mov     rcx, rdi; AbsoluteSD
0x18005abc3  call    cs:__imp_RtlMakeSelfRelativeSD
0x18005abc9  mov     ecx, eax; Status
0x18005abcb  call    cs:__imp_RtlNtStatusToDosError
0x18005abd1  mov     r12d, eax
0x18005abd4  test    r12d, r12d
0x18005abd7  jnz     loc_18005A977
0x18005abdd  mov     eax, [rbx]
0x18005abdf  mov     [rsp+0E8h+var_58], eax
0x18005abe6  movzx   eax, byte ptr [rbx+10h]
0x18005abea  mov     [rsp+0E8h+var_40], al
0x18005abf1  test    r12d, r12d
0x18005abf4  jnz     loc_18005A977
0x18005abfa  lea     rbx, [rsp+0E8h+var_58]
0x18005ac02  jmp     loc_18005A8F3
0x18005ac07  mov     rdx, rdi; SourceString
0x18005ac0a  lea     rcx, [rsp+0E8h+var_78]; DestinationString
0x18005ac0f  call    cs:__imp_RtlInitUnicodeStringEx
0x18005ac15  test    eax, eax
0x18005ac17  js      loc_18005ADB2
0x18005ac1d  add     [rsp+0E8h+var_78.Length], 2
0x18005ac23  jmp     loc_18005A8DF
0x18005ac28  mov     r12d, 57h ; 'W'
0x18005ac2e  jmp     short loc_18005ABD4
0x18005ac30  call    IsBaseRegCloseKeyPresent
0x18005ac35  test    al, al
0x18005ac37  jz      loc_18005AA32
0x18005ac3d  lea     rcx, [rsp+0E8h+Handle]
0x18005ac42  call    cs:__imp_PerfRegCloseKey
0x18005ac48  jmp     loc_18005AA32
0x18005ac4d  cmp     [rsp+0E8h+BufferLength], r15d
0x18005ac55  jnb     loc_18005ABAD
0x18005ac5b  mov     r12d, 0Eh
0x18005ac61  jmp     loc_18005ABD4
0x18005ac66  mov     qword ptr [rsp+0E8h+BufferLength], rsi
0x18005ac6e  mov     r12d, esi
0x18005ac71  jmp     loc_18005ABDD
0x18005ac76  mov     r12d, 0Eh
0x18005ac7c  jmp     loc_18005ABD4
0x18005ac81  mov     eax, 6
0x18005ac86  jmp     loc_18005AA3A
0x18005ac8b  mov     ecx, eax; Status
0x18005ac8d  call    cs:__imp_RtlNtStatusToDosError
0x18005ac93  jmp     loc_18005AA32
0x18005ac98  call    IsBaseRegCloseKeyPresent
0x18005ac9d  test    al, al
0x18005ac9f  jz      loc_18005A959
0x18005aca5  mov     dword ptr [rsp+0E8h+KeyHandle], esi
0x18005acac  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18005acb0  call    IsBaseRegCloseKeyPresent
0x18005acb5  test    al, al
0x18005acb7  jnz     loc_18005AD6C
0x18005acbd  xor     dl, dl
0x18005acbf  mov     ecx, [rsp+0E8h+arg_28]
0x18005acc6  and     ecx, 0FFFFFCFFh
0x18005accc  test    dl, dl
0x18005acce  cmovnz  ecx, [rsp+0E8h+arg_28]
0x18005acd6  mov     rax, [rsp+0E8h+arg_40]
0x18005acde  mov     [rsp+0E8h+var_B0], rax
0x18005ace3  mov     [rsp+0E8h+var_B8], r14
0x18005ace8  mov     [rsp+0E8h+var_C0], rbx
0x18005aced  mov     [rsp+0E8h+var_C8], ecx
0x18005acf1  mov     r9d, [rsp+0E8h+arg_20]
0x18005acf9  lea     r8, [rsp+0E8h+var_78]
0x18005acfe  lea     rdx, [rsp+0E8h+DestinationString]
0x18005ad06  mov     rcx, rdi
0x18005ad09  call    cs:__imp_BaseRegCreateKey
0x18005ad0f  mov     r12d, eax
0x18005ad12  mov     [rsp+0E8h+var_98], eax
0x18005ad16  jmp     short loc_18005AD2E
0x18005ad18  mov     r12d, eax
0x18005ad1b  mov     [rsp+0E8h+var_98], eax
0x18005ad1f  xor     esi, esi
0x18005ad21  mov     r14, [rsp+0E8h+arg_38]
0x18005ad29  mov     rbx, [rsp+0E8h+Handle]
0x18005ad2e  test    r12d, r12d
0x18005ad31  jnz     loc_18005A959
0x18005ad37  or      qword ptr [r14], 1
0x18005ad3b  jmp     loc_18005A959
0x18005ad40  mov     eax, 57h ; 'W'
0x18005ad45  add     rsp, 0B8h
0x18005ad4c  pop     r15
0x18005ad4e  pop     r14
0x18005ad50  pop     r12
  ... truncated ...
```
