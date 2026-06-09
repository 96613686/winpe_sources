# BipCreatePackageAndPackageInstance

- ea: `0x18002beb8`
- end: `0x18002c0a9`
- name: `BipCreatePackageAndPackageInstance`
- size: `497`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b95c`
- `0x18002ba58`
- `0x18002bcb8`
- `0x18002d5e0`

## callees

- `0x1800054d4`
- `0x18002a410`
- `0x18002b060`
- `0x18002beb8`
- `0x18002c3b0`
- `0x180035d28`
- `0x18003f218`
- `0x180040b94`
- `0x180043010`
- `0x180053100`
- `0x180056e40`
- `0x18006d364`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlInsertEntryHashTable` at `0x18002bf96`
- `ntdll!RtlInsertEntryHashTable` at `0x18002bf96`
- `ntdll!RtlFreeHeap` at `0x18002bfcf`
- `ntdll!RtlFreeHeap` at `0x18002bfcf`
- `ntdll!RtlAllocateHeap` at `0x18002bf0c`
- `ntdll!RtlAllocateHeap` at `0x18002bf0c`
- `ntdll!RtlLengthSid` at `0x18002bef4`
- `ntdll!RtlLengthSid` at `0x18002bef4`

## pseudocode

```c
__int64 __fastcall BipCreatePackageAndPackageInstance(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  ULONG v9; // ebx
  PVOID Heap; // rax
  __int64 v11; // r8
  void *v12; // rdi
  int State; // ebx
  __int64 PackageInstance; // rsi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  int v21; // [rsp+30h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+40h] [rbp-A8h] BYREF
  unsigned __int8 *v23; // [rsp+60h] [rbp-88h]
  int v24; // [rsp+68h] [rbp-80h]
  int v25; // [rsp+6Ch] [rbp-7Ch]
  char v26[16]; // [rsp+70h] [rbp-78h] BYREF
  int *v27; // [rsp+80h] [rbp-68h]
  __int64 v28; // [rsp+88h] [rbp-60h]

  v9 = RtlLengthSid(a4);
  Heap = RtlAllocateHeap(BipHeap, 0, v9 + 616);
  v12 = Heap;
  if ( !Heap )
  {
    State = -1073741801;
LABEL_13:
    if ( (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v11) )
    {
      v19 = a4[1];
      v23 = a4;
      v25 = 0;
      v24 = 4 * v19 + 8;
      tlgCreate1Sz_wchar_t(v26, a3);
      v21 = State;
      v27 = &v21;
      v28 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800C3098, (unsigned __int8 *)&unk_1800AF600, 0, 0, 5u, &v22);
    }
    return (unsigned int)State;
  }
  BipPackageInitialize(Heap, a3, a4, v9);
  State = BipPackageAllocateState((__int64)v12);
  if ( State < 0 )
  {
LABEL_12:
    BipPackageCleanup(v12);
    RtlFreeHeap(BipHeap, 0, v12);
    goto LABEL_13;
  }
  PackageInstance = 0;
  if ( a5 != -1 )
  {
    PackageInstance = BipCreatePackageInstance(v12, a5);
    if ( !PackageInstance )
    {
      State = -1073741801;
      goto LABEL_12;
    }
  }
  State = BipEnergyBudgetPackageCreated(qword_1800C45C0);
  if ( State < 0 )
  {
LABEL_10:
    if ( PackageInstance )
      BipDeletePackageInstance(PackageInstance);
    goto LABEL_12;
  }
  v15 = BipCalculateHashSignatureForPackage(a3, a4);
  if ( !(unsigned __int8)RtlInsertEntryHashTable(qword_1800C4380, v12, v15, 0) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18);
    State = -1073741823;
    goto LABEL_10;
  }
  *a1 = v12;
  if ( a2 )
    *a2 = PackageInstance;
  return 0;
}

```

## disassembly

```asm
0x18002beb8  push    rbx
0x18002beba  push    rbp
0x18002bebb  push    rsi
0x18002bebc  push    rdi
0x18002bebd  push    r12
0x18002bebf  push    r13
0x18002bec1  push    r14
0x18002bec3  push    r15
0x18002bec5  sub     rsp, 0A8h
0x18002becc  mov     rax, cs:__security_cookie
0x18002bed3  xor     rax, rsp
0x18002bed6  mov     [rsp+0E8h+var_58], rax
0x18002bede  mov     ebp, [rsp+0E8h+arg_20]
0x18002bee5  mov     r13, rcx
0x18002bee8  mov     rcx, r9; Sid
0x18002beeb  mov     r14, r9
0x18002beee  mov     r12, r8
0x18002bef1  mov     r15, rdx
0x18002bef4  call    cs:__imp_RtlLengthSid
0x18002befa  mov     rcx, cs:BipHeap; HeapHandle
0x18002bf01  xor     edx, edx; Flags
0x18002bf03  mov     ebx, eax
0x18002bf05  lea     r8d, [rax+268h]; Size
0x18002bf0c  call    cs:__imp_RtlAllocateHeap
0x18002bf12  mov     rdi, rax
0x18002bf15  test    rax, rax
0x18002bf18  jnz     short loc_18002BF24
0x18002bf1a  mov     ebx, 0C0000017h
0x18002bf1f  jmp     loc_18002BFDD
0x18002bf24  mov     r9d, ebx
0x18002bf27  mov     r8, r14
0x18002bf2a  mov     rdx, r12
0x18002bf2d  mov     rcx, rdi
0x18002bf30  call    BipPackageInitialize
0x18002bf35  mov     rcx, rdi
0x18002bf38  call    BipPackageAllocateState
0x18002bf3d  mov     ebx, eax
0x18002bf3f  test    eax, eax
0x18002bf41  js      short loc_18002BFBB
0x18002bf43  xor     esi, esi
0x18002bf45  cmp     ebp, 0FFFFFFFFh
0x18002bf48  jz      short loc_18002BF63
0x18002bf4a  mov     edx, ebp
0x18002bf4c  mov     rcx, rdi
0x18002bf4f  call    BipCreatePackageInstance
0x18002bf54  mov     rsi, rax
0x18002bf57  test    rax, rax
0x18002bf5a  jnz     short loc_18002BF63
0x18002bf5c  mov     ebx, 0C0000017h
0x18002bf61  jmp     short loc_18002BFBB
0x18002bf63  mov     rcx, cs:qword_1800C45C0; struct _BI_LOCK *
0x18002bf6a  mov     r8d, ebp
0x18002bf6d  mov     rdx, rdi
0x18002bf70  call    BipEnergyBudgetPackageCreated
0x18002bf75  mov     ebx, eax
0x18002bf77  test    eax, eax
0x18002bf79  js      short loc_18002BFAE
0x18002bf7b  mov     rdx, r14
0x18002bf7e  mov     rcx, r12
0x18002bf81  call    BipCalculateHashSignatureForPackage
0x18002bf86  mov     rcx, cs:qword_1800C4380
0x18002bf8d  xor     r9d, r9d
0x18002bf90  mov     r8, rax
0x18002bf93  mov     rdx, rdi
0x18002bf96  call    cs:__imp_RtlInsertEntryHashTable
0x18002bf9c  test    al, al
0x18002bf9e  jnz     loc_18002C099
0x18002bfa4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bfa9  mov     ebx, 0C0000001h
0x18002bfae  test    rsi, rsi
0x18002bfb1  jz      short loc_18002BFBB
0x18002bfb3  mov     rcx, rsi
0x18002bfb6  call    BipDeletePackageInstance
0x18002bfbb  mov     rcx, rdi
0x18002bfbe  call    BipPackageCleanup
0x18002bfc3  mov     rcx, cs:BipHeap; HeapHandle
0x18002bfca  mov     r8, rdi; P
0x18002bfcd  xor     edx, edx; Flags
0x18002bfcf  call    cs:__imp_RtlFreeHeap
0x18002bfd5  test    ebx, ebx
0x18002bfd7  jns     loc_18002C073
0x18002bfdd  mov     eax, cs:dword_1800C3098
0x18002bfe3  cmp     eax, 2
0x18002bfe6  jbe     loc_18002C073
0x18002bfec  mov     edx, 3
0x18002bff1  lea     rcx, dword_1800C3098
0x18002bff8  call    _tlgKeywordOn
0x18002bffd  test    al, al
0x18002bfff  jz      short loc_18002C073
0x18002c001  movzx   eax, byte ptr [r14+1]
0x18002c006  lea     rcx, [rsp+0E8h+var_78]
0x18002c00b  mov     rdx, r12
0x18002c00e  mov     [rsp+0E8h+var_88], r14
0x18002c013  mov     [rsp+0E8h+var_7C], 0
0x18002c01b  lea     eax, ds:8[rax*4]
0x18002c022  mov     [rsp+0E8h+var_80], eax
0x18002c026  call    _tlgCreate1Sz_wchar_t
0x18002c02b  lea     rax, [rsp+0E8h+var_B8]
0x18002c030  mov     [rsp+0E8h+var_B8], ebx
0x18002c034  mov     [rsp+0E8h+var_68], rax
0x18002c03c  lea     rdx, unk_1800AF600
0x18002c043  lea     rax, [rsp+0E8h+var_A8]
0x18002c048  mov     [rsp+0E8h+var_60], 4
0x18002c054  mov     [rsp+0E8h+var_C0], rax
0x18002c059  lea     rcx, dword_1800C3098
0x18002c060  xor     r9d, r9d
0x18002c063  mov     [rsp+0E8h+var_C8], 5
0x18002c06b  xor     r8d, r8d
0x18002c06e  call    _tlgWriteTransfer_EventWriteTransfer
0x18002c073  mov     eax, ebx
0x18002c075  mov     rcx, [rsp+0E8h+var_58]
0x18002c07d  xor     rcx, rsp; StackCookie
0x18002c080  call    __security_check_cookie
0x18002c085  add     rsp, 0A8h
0x18002c08c  pop     r15
0x18002c08e  pop     r14
0x18002c090  pop     r13
0x18002c092  pop     r12
0x18002c094  pop     rdi
0x18002c095  pop     rsi
0x18002c096  pop     rbp
0x18002c097  pop     rbx
0x18002c098  retn
0x18002c099  mov     [r13+0], rdi
0x18002c09d  test    r15, r15
0x18002c0a0  jz      short loc_18002C0A5
0x18002c0a2  mov     [r15], rsi
0x18002c0a5  xor     ebx, ebx
0x18002c0a7  jmp     short loc_18002C073
```
