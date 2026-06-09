# ABO_WRAPPER::GetAllData(ulong,ushort const *,ulong,ulong,ulong,ulong *,ulong *,ulong,uchar *,ulong *)

- ea: `0x18000d7a0`
- end: `0x18000d8e7`
- name: `?GetAllData@ABO_WRAPPER@@UEAAJKPEBGKKKPEAK1KPEAE1@Z`
- size: `327`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180003f14`
- `0x18000672c`
- `0x18000d7a0`
- `0x18000d8f0`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000fab8`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d88d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d88d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d7ff`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d7ff`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetAllData(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int *a11)
{
  HANDLE_ENTRY *v12; // rdi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  HANDLE_ENTRY *v18; // [rsp+50h] [rbp-30h] BYREF
  struct ABO_TREE *v19; // [rsp+58h] [rbp-28h] BYREF
  void **v20; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v21[3]; // [rsp+68h] [rbp-18h] BYREF

  v18 = 0;
  v21[0] = 0;
  v12 = 0;
  v20 = &PROPERTY_BAG::`vftable';
  v19 = 0;
  v21[1] = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v18);
  if ( HandleEntry >= 0 )
  {
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
    CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v19);
    v12 = v19;
    HandleEntry = CurrentAboTree;
    if ( CurrentAboTree >= 0 )
    {
      HandleEntry = ABO_WRAPPER::GetAllDataInternal(this, v18, a3, v19, a4, a5, a6, a8, (struct PROPERTY_BAG *)&v20);
      if ( HandleEntry >= 0 )
        HandleEntry = PROPERTY_BAG::CopyAllToBuffer((PROPERTY_BAG *)&v20, a4, a7, a9, a10, a11);
    }
    CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
  }
  if ( v18 )
    HANDLE_ENTRY::DereferenceHandleEntry(v18);
  if ( v12 )
    HANDLE_ENTRY::DereferenceHandleEntry(v12);
  v20 = &PROPERTY_BAG::`vftable';
  if ( HandleEntry == -2147024894 )
    HandleEntry = -2146646015;
  ARRAY_LIST::~ARRAY_LIST((ARRAY_LIST *)v21);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000d7a0  push    rbp
0x18000d7a2  push    rbx
0x18000d7a3  push    rdi
0x18000d7a4  push    r12
0x18000d7a6  push    r13
0x18000d7a8  push    r14
0x18000d7aa  push    r15
0x18000d7ac  mov     rbp, rsp
0x18000d7af  sub     rsp, 80h
0x18000d7b6  mov     r13, r8
0x18000d7b9  mov     [rbp+var_30], 0
0x18000d7c1  lea     r15, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x18000d7c8  mov     [rbp+var_18], 0
0x18000d7d0  xor     edi, edi
0x18000d7d2  mov     [rbp+var_20], r15
0x18000d7d6  lea     r8, [rbp+var_30]; struct HANDLE_ENTRY **
0x18000d7da  mov     [rbp+var_28], rdi
0x18000d7de  mov     r12d, r9d
0x18000d7e1  mov     [rbp+var_10], 0
0x18000d7e9  mov     r14, rcx
0x18000d7ec  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000d7f1  mov     ebx, eax
0x18000d7f3  test    eax, eax
0x18000d7f5  js      loc_18000D89A
0x18000d7fb  lea     rcx, [r14+20h]
0x18000d7ff  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d805  lea     rdx, [rbp+var_28]; struct ABO_TREE **
0x18000d809  mov     rcx, r14; this
0x18000d80c  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000d811  mov     rdi, [rbp+var_28]
0x18000d815  mov     ebx, eax
0x18000d817  test    eax, eax
0x18000d819  js      short loc_18000D889
0x18000d81b  mov     rdx, [rbp+var_30]; struct HANDLE_ENTRY *
0x18000d81f  lea     rax, [rbp+var_20]
0x18000d823  mov     [rsp+80h+var_40], rax; struct PROPERTY_BAG *
0x18000d828  mov     r9, rdi; struct ABO_TREE *
0x18000d82b  mov     rax, [rbp+arg_38]
0x18000d82f  mov     r8, r13; unsigned __int16 *
0x18000d832  mov     [rsp+80h+var_48], rax; unsigned int *
0x18000d837  mov     rcx, r14; this
0x18000d83a  mov     eax, [rbp+arg_28]
0x18000d83d  mov     [rsp+80h+var_50], eax; unsigned int
0x18000d841  mov     eax, [rbp+arg_20]
0x18000d844  mov     dword ptr [rsp+80h+var_58], eax; unsigned int
0x18000d848  mov     dword ptr [rsp+80h+var_60], r12d; unsigned int
0x18000d84d  call    ?GetAllDataInternal@ABO_WRAPPER@@AEAAJPEAVHANDLE_ENTRY@@PEBGPEAVABO_TREE@@KKKPEAKPEAVPROPERTY_BAG@@@Z; ABO_WRAPPER::GetAllDataInternal(HANDLE_ENTRY *,ushort const *,ABO_TREE *,ulong,ulong,ulong,ulong *,PROPERTY_BAG *)
0x18000d852  mov     ebx, eax
0x18000d854  test    eax, eax
0x18000d856  js      short loc_18000D889
0x18000d858  mov     rax, [rbp+arg_50]
0x18000d85f  lea     rcx, [rbp+var_20]; this
0x18000d863  mov     r9d, [rbp+arg_40]; unsigned int
0x18000d86a  mov     edx, r12d; unsigned int
0x18000d86d  mov     r8, [rbp+arg_30]; unsigned int *
0x18000d871  mov     [rsp+80h+var_58], rax; unsigned int *
0x18000d876  mov     rax, [rbp+arg_48]
0x18000d87d  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x18000d882  call    ?CopyAllToBuffer@PROPERTY_BAG@@QEAAJKPEAKKPEAE0@Z; PROPERTY_BAG::CopyAllToBuffer(ulong,ulong *,ulong,uchar *,ulong *)
0x18000d887  mov     ebx, eax
0x18000d889  lea     rcx, [r14+20h]
0x18000d88d  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d893  lea     r15, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x18000d89a  cmp     [rbp+var_30], 0
0x18000d89f  jz      short loc_18000D8AA
0x18000d8a1  mov     rcx, [rbp+var_30]; this
0x18000d8a5  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d8aa  test    rdi, rdi
0x18000d8ad  jz      short loc_18000D8B7
0x18000d8af  mov     rcx, rdi; this
0x18000d8b2  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d8b7  cmp     ebx, 80070002h
0x18000d8bd  mov     [rbp+var_20], r15
0x18000d8c1  mov     eax, 800CC801h
0x18000d8c6  lea     rcx, [rbp+var_18]; this
0x18000d8ca  cmovz   ebx, eax
0x18000d8cd  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x18000d8d2  mov     eax, ebx
0x18000d8d4  add     rsp, 80h
0x18000d8db  pop     r15
0x18000d8dd  pop     r14
0x18000d8df  pop     r13
0x18000d8e1  pop     r12
0x18000d8e3  pop     rdi
0x18000d8e4  pop     rbx
0x18000d8e5  pop     rbp
0x18000d8e6  retn
```
