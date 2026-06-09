# AhcpCdbLoadFromPdb

- ea: `0x14004b4ac`
- end: `0x14004b65e`
- name: `AhcpCdbLoadFromPdb`
- size: `434`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Parameter, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140024c1c`

## callees

- `0x1400040e4`
- `0x14003b570`
- `0x14003c19c`
- `0x14003d820`
- `0x14003e364`
- `0x14003ef10`
- `0x14004b4ac`
- `0x14004b664`
- `0x14004b704`
- `0x14004bd80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14004b56a`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14004b56a`

## string_xrefs

- `0x14004b5f2`: `Failed to insert to cache [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCdbLoadFromPdb(PRTL_AVL_TABLE Table, PVOID Parameter, __int64 a3, int a4)
{
  int v8; // edx
  int v9; // r8d
  unsigned int FirstDWORDIndexedTag; // eax
  unsigned int i; // edi
  const WCHAR *StringTagPtr; // rax
  NTSTATUS inited; // eax
  unsigned int v14; // ebx
  unsigned int NextIndexedRecord; // eax
  const char *v16; // r9
  __int64 v17; // r8
  __int64 v19; // [rsp+20h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v21[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+68h] [rbp-8h]

  v22 = 0;
  memset(v21, 0, sizeof(v21));
  DestinationString = 0;
  if ( (unsigned int)SdbGetIndex(Parameter) )
  {
    FirstDWORDIndexedTag = SdbFindFirstDWORDIndexedTag((_DWORD)Parameter, v8, v9, a4, (__int64)v21);
LABEL_3:
    for ( i = FirstDWORDIndexedTag; i; i = 0 )
    {
      if ( (unsigned int)SdbFindFirstTag(Parameter, i, 24577) )
      {
        StringTagPtr = (const WCHAR *)SdbGetStringTagPtr(Parameter);
        if ( StringTagPtr )
        {
          inited = RtlInitUnicodeStringEx(&DestinationString, StringTagPtr);
          v14 = inited;
          if ( inited < 0 )
          {
            v16 = "Failed to initialize key name [%x]";
            v17 = 719;
            goto LABEL_18;
          }
          if ( !(unsigned int)SdbFindFirstTag(Parameter, i, 4120)
            && (!a3 || !(unsigned int)QuirksIsEntryIdAvailableInOtherDb(Parameter, a3, i)) )
          {
            inited = AhcStoreUpdate(Table);
            v14 = inited;
            if ( inited < 0 )
            {
              v16 = "Failed to insert to cache [%x]";
              v17 = 745;
LABEL_18:
              LODWORD(v19) = inited;
              AslLogCallPrintf(1, "AhcpCdbLoadFromPdb", v17, v16, v19);
              return v14;
            }
          }
        }
        else
        {
          AslLogCallPrintf(1, "AhcpCdbLoadFromPdb", 713, "Failed to get the name string");
        }
      }
      NextIndexedRecord = SdbpGetNextIndexedRecord(Parameter, LODWORD(v21[0]), v21);
      if ( NextIndexedRecord )
      {
        FirstDWORDIndexedTag = SdbpFindMatchingDWORD(Parameter, NextIndexedRecord, v21);
        goto LABEL_3;
      }
    }
    return 0;
  }
  else
  {
    AslLogCallPrintf(1, "AhcpCdbLoadFromPdb", 686, "Sdb index is not available");
    return (unsigned int)-1073741275;
  }
}

```

## disassembly

```asm
0x14004b4ac  push    rbp
0x14004b4ae  push    rbx
0x14004b4af  push    rsi
0x14004b4b0  push    rdi
0x14004b4b1  push    r12
0x14004b4b3  push    r13
0x14004b4b5  push    r15
0x14004b4b7  mov     rbp, rsp
0x14004b4ba  sub     rsp, 70h
0x14004b4be  xorps   xmm0, xmm0
0x14004b4c1  mov     rsi, rdx
0x14004b4c4  xor     eax, eax
0x14004b4c6  mov     r12d, r9d
0x14004b4c9  mov     r15, r8
0x14004b4cc  mov     [rbp+var_8], rax
0x14004b4d0  mov     r13, rcx
0x14004b4d3  mov     [rbp+var_40], eax
0x14004b4d6  mov     rcx, rsi; Parameter
0x14004b4d9  mov     edx, 7007h
0x14004b4de  mov     r8d, 4032h
0x14004b4e4  xor     r9d, r9d
0x14004b4e7  movups  [rbp+var_28], xmm0
0x14004b4eb  movups  [rbp+var_18], xmm0
0x14004b4ef  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004b4f3  call    SdbGetIndex
0x14004b4f8  test    eax, eax
0x14004b4fa  jz      loc_14004B629
0x14004b500  lea     rax, [rbp+var_28]
0x14004b504  mov     r9d, r12d
0x14004b507  mov     rcx, rsi
0x14004b50a  mov     [rsp+70h+var_50], rax
0x14004b50f  call    SdbFindFirstDWORDIndexedTag
0x14004b514  mov     edi, eax
0x14004b516  test    edi, edi
0x14004b518  jz      loc_14004B625
0x14004b51e  mov     r8d, 6001h
0x14004b524  mov     edx, edi
0x14004b526  mov     rcx, rsi
0x14004b529  call    SdbFindFirstTag
0x14004b52e  test    eax, eax
0x14004b530  jz      loc_14004B5C5
0x14004b536  mov     edx, eax
0x14004b538  mov     rcx, rsi
0x14004b53b  call    SdbGetStringTagPtr
0x14004b540  test    rax, rax
0x14004b543  jnz     short loc_14004B563
0x14004b545  lea     r9, aFailedToGetThe_6; "Failed to get the name string"
0x14004b54c  mov     r8d, 2C9h
0x14004b552  lea     rdx, aAhcpcdbloadfro; "AhcpCdbLoadFromPdb"
0x14004b559  lea     ecx, [rax+1]
0x14004b55c  call    AslLogCallPrintf
0x14004b561  jmp     short loc_14004B5C5
0x14004b563  mov     rdx, rax; SourceString
0x14004b566  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004b56a  call    cs:__imp_RtlInitUnicodeStringEx
0x14004b571  nop     dword ptr [rax+rax+00h]
0x14004b576  mov     ebx, eax
0x14004b578  test    eax, eax
0x14004b57a  js      loc_14004B601
0x14004b580  mov     r8d, 1018h
0x14004b586  mov     edx, edi
0x14004b588  mov     rcx, rsi
0x14004b58b  call    SdbFindFirstTag
0x14004b590  test    eax, eax
0x14004b592  jnz     short loc_14004B5C5
0x14004b594  test    r15, r15
0x14004b597  jz      short loc_14004B5AB
0x14004b599  mov     r8d, edi
0x14004b59c  mov     rdx, r15
0x14004b59f  mov     rcx, rsi
0x14004b5a2  call    QuirksIsEntryIdAvailableInOtherDb
0x14004b5a7  test    eax, eax
0x14004b5a9  jnz     short loc_14004B5C5
0x14004b5ab  lea     r8, [rbp+var_40]
0x14004b5af  mov     [rbp+var_40], r12d
0x14004b5b3  lea     rdx, [rbp+DestinationString]
0x14004b5b7  mov     rcx, r13; Table
0x14004b5ba  call    AhcStoreUpdate
0x14004b5bf  mov     ebx, eax
0x14004b5c1  test    eax, eax
0x14004b5c3  js      short loc_14004B5F2
0x14004b5c5  mov     edx, dword ptr [rbp+var_28]
0x14004b5c8  lea     r8, [rbp+var_28]
0x14004b5cc  mov     rcx, rsi
0x14004b5cf  call    SdbpGetNextIndexedRecord
0x14004b5d4  test    eax, eax
0x14004b5d6  jnz     short loc_14004B5DF
0x14004b5d8  xor     edi, edi
0x14004b5da  jmp     loc_14004B516
0x14004b5df  lea     r8, [rbp+var_28]
0x14004b5e3  mov     edx, eax
0x14004b5e5  mov     rcx, rsi
0x14004b5e8  call    SdbpFindMatchingDWORD
0x14004b5ed  jmp     loc_14004B514
0x14004b5f2  lea     r9, aFailedToInsert_3; "Failed to insert to cache [%x]"
0x14004b5f9  mov     r8d, 2E9h
0x14004b5ff  jmp     short loc_14004B60E
0x14004b601  lea     r9, aFailedToInitia_8; "Failed to initialize key name [%x]"
0x14004b608  mov     r8d, 2CFh
0x14004b60e  lea     rdx, aAhcpcdbloadfro; "AhcpCdbLoadFromPdb"
0x14004b615  mov     dword ptr [rsp+70h+var_50], eax
0x14004b619  mov     ecx, 1
0x14004b61e  call    AslLogCallPrintf
0x14004b623  jmp     short loc_14004B64C
0x14004b625  xor     ebx, ebx
0x14004b627  jmp     short loc_14004B64C
0x14004b629  lea     r9, aSdbIndexIsNotA; "Sdb index is not available"
0x14004b630  mov     r8d, 2AEh
0x14004b636  lea     rdx, aAhcpcdbloadfro; "AhcpCdbLoadFromPdb"
0x14004b63d  mov     ecx, 1
0x14004b642  call    AslLogCallPrintf
0x14004b647  mov     ebx, 0C0000225h
0x14004b64c  mov     eax, ebx
0x14004b64e  add     rsp, 70h
0x14004b652  pop     r15
0x14004b654  pop     r13
0x14004b656  pop     r12
0x14004b658  pop     rdi
0x14004b659  pop     rsi
0x14004b65a  pop     rbx
0x14004b65b  pop     rbp
0x14004b65c  retn
```
