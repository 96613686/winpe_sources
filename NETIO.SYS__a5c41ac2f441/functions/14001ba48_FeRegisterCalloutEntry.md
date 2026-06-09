# FeRegisterCalloutEntry

- ea: `0x14001ba48`
- end: `0x14001bd1d`
- name: `FeRegisterCalloutEntry`
- size: `725`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, char, unsigned int, PVOID Object, __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001bd30`

## callees

- `0x140009520`
- `0x140009e00`
- `0x1400119a4`
- `0x140011a64`
- `0x140011b70`
- `0x14001ba48`
- `0x14001bdf0`
- `0x14001cfe0`
- `0x14001d050`
- `0x140045244`
- `0x1400477c4`
- `0x140065c8c`
- `0x140069750`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14001bc96`
- `ntoskrnl!IoFreeWorkItem` at `0x14001bcd3`
- `ntoskrnl!IoFreeWorkItem` at `0x14001bc96`
- `ntoskrnl!IoFreeWorkItem` at `0x14001bcd3`
- `ntoskrnl!ObfReferenceObject` at `0x14001bb92`
- `ntoskrnl!ObfReferenceObject` at `0x14001bb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bce7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bce7`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x14001bc87`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x14001bcc4`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x14001bc87`
- `NDIS!NdisNblTrackerDeregisterComponent` at `0x14001bcc4`

## pseudocode

```c
__int64 __fastcall FeRegisterCalloutEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        unsigned int a7,
        PVOID Object,
        __int16 a9)
{
  int v10; // r13d
  __int64 v11; // r8
  const char *v12; // rdx
  __int64 NblTrackerContext; // rsi
  __int64 CalloutEntry; // rdi
  __int64 v15; // rbx
  char v16; // bp
  char v17; // r15
  char v18; // r14
  __int64 v19; // rcx
  __int16 v21; // [rsp+20h] [rbp-38h] BYREF
  char v22; // [rsp+22h] [rbp-36h]

  v10 = a1;
  v21 = 0;
  v22 = 0;
  if ( a7 > 0x186A0 )
  {
    v11 = 3221225485LL;
    v12 = "FeRegisterCalloutEntry";
LABEL_6:
    CalloutEntry = WfpReportSysErrorAsNtStatus(a1, v12, v11, 1);
    goto LABEL_7;
  }
  NblTrackerContext = 0;
  if ( NetioNblTrackerEnabled )
  {
    NblTrackerContext = FeAllocateNblTrackerContext(Object, a2, a7);
    if ( !NblTrackerContext )
    {
      v11 = 3221225495LL;
      v12 = "FeAllocateNblTrackerContext";
      goto LABEL_6;
    }
  }
  CalloutEntry = FeAcquireWriteEngineLock(&v21, 0);
  if ( CalloutEntry )
  {
    if ( NblTrackerContext )
    {
      NdisNblTrackerDeregisterComponent(*(_QWORD *)(NblTrackerContext + 8));
      IoFreeWorkItem(*(PIO_WORKITEM *)NblTrackerContext);
      ExFreePoolWithTag((PVOID)NblTrackerContext, 0x43706657u);
    }
    goto LABEL_40;
  }
  CalloutEntry = WfpAllocateCalloutEntry(a7);
  if ( !CalloutEntry )
  {
    v15 = *(_QWORD *)&gWfpGlobal[3].L.Tag + 144LL * a7;
    CalloutEntry = IsCalloutEntryAvailable(v15);
    if ( !CalloutEntry )
    {
      *(_DWORD *)v15 = v10;
      v16 = 1;
      *(_DWORD *)(v15 + 4) = 1;
      if ( v10 == 3 )
        *(_QWORD *)(v15 + 48) = a2;
      else
        *(_QWORD *)(v15 + 24) = a2;
      *(_QWORD *)(v15 + 32) = a3;
      *(_QWORD *)(v15 + 40) = a4;
      *(_DWORD *)(v15 + 56) = a5;
      *(_BYTE *)(v15 + 118) = a6;
      if ( Object )
      {
        ObfReferenceObject(Object);
        *(_QWORD *)(v15 + 104) = Object;
      }
      *(_WORD *)(v15 + 116) = a9;
      if ( !*(_DWORD *)(v15 + 124) || (v17 = 1, (*(_DWORD *)(v15 + 56) & 0x40) != 0) )
        v17 = 0;
      if ( !*(_DWORD *)(v15 + 128) || (v18 = 1, (*(_DWORD *)(v15 + 56) & 0x100) != 0) )
        v18 = 0;
      if ( !*(_DWORD *)(v15 + 132) || (*(_DWORD *)(v15 + 56) & 0x200) != 0 )
        v16 = 0;
      if ( *(_BYTE *)(v15 + 12) && dword_14009A098 && (unsigned __int8)tlgKeywordOn(&dword_14009A098, 2) )
        WfpCalloutDiagTraceCalloutAddOrRegister(a7, v15);
      *(_QWORD *)(v15 + 136) = NblTrackerContext;
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &v21);
      if ( v17 )
        KfdNotifyRscIncompatCalloutAdd(v19);
      if ( v18 )
        KfdNotifyUsoIncompatCallout(0);
      if ( v16 )
        KfdNotifyUroIncompatCallout(0);
      return CalloutEntry;
    }
  }
  WfpReleaseFastWriteLock(&gWfpGlobal[1], &v21);
  if ( !NblTrackerContext )
  {
LABEL_40:
    WfpReportError(CalloutEntry, "FeRegisterCalloutEntry");
    return CalloutEntry;
  }
  NdisNblTrackerDeregisterComponent(*(_QWORD *)(NblTrackerContext + 8));
  IoFreeWorkItem(*(PIO_WORKITEM *)NblTrackerContext);
  ExFreePoolWithTag((PVOID)NblTrackerContext, 0x43706657u);
LABEL_7:
  if ( CalloutEntry )
    goto LABEL_40;
  return CalloutEntry;
}

```

## disassembly

```asm
0x14001ba48  mov     rax, rsp
0x14001ba4b  mov     [rax+8], rbx
0x14001ba4f  mov     [rax+10h], rbp
0x14001ba53  mov     [rax+20h], r9
0x14001ba57  mov     [rax+18h], r8
0x14001ba5b  push    rsi
0x14001ba5c  push    rdi
0x14001ba5d  push    r13
0x14001ba5f  push    r14
0x14001ba61  push    r15
0x14001ba63  sub     rsp, 30h
0x14001ba67  xor     eax, eax
0x14001ba69  mov     r15, rdx
0x14001ba6c  cmp     [rsp+58h+arg_30], 186A0h
0x14001ba77  mov     r13d, ecx
0x14001ba7a  mov     [rsp+58h+var_38], ax
0x14001ba7f  mov     [rsp+58h+var_36], al
0x14001ba83  jbe     short loc_14001BA94
0x14001ba85  mov     r8d, 0C000000Dh
0x14001ba8b  lea     rdx, aFeregistercall; "FeRegisterCalloutEntry"
0x14001ba92  jmp     short loc_14001BACB
0x14001ba94  mov     r14, [rsp+58h+Object]
0x14001ba9c  xor     esi, esi
0x14001ba9e  cmp     cs:NetioNblTrackerEnabled, al
0x14001baa4  jz      short loc_14001BAE7
0x14001baa6  mov     r8d, [rsp+58h+arg_30]
0x14001baae  mov     rcx, r14
0x14001bab1  call    FeAllocateNblTrackerContext
0x14001bab6  mov     rsi, rax
0x14001bab9  test    rax, rax
0x14001babc  jnz     short loc_14001BAE7
0x14001babe  mov     r8d, 0C0000017h
0x14001bac4  lea     rdx, aFeallocatenblt; "FeAllocateNblTrackerContext"
0x14001bacb  mov     r9d, 1
0x14001bad1  call    WfpReportSysErrorAsNtStatus
0x14001bad6  mov     rdi, rax
0x14001bad9  test    rdi, rdi
0x14001badc  jz      loc_14001BD02
0x14001bae2  jmp     loc_14001BCF3
0x14001bae7  xor     edx, edx
0x14001bae9  lea     rcx, [rsp+58h+var_38]
0x14001baee  call    FeAcquireWriteEngineLock
0x14001baf3  mov     rdi, rax
0x14001baf6  test    rax, rax
0x14001baf9  jnz     loc_14001BCBB
0x14001baff  mov     ecx, [rsp+58h+arg_30]
0x14001bb06  call    WfpAllocateCalloutEntry
0x14001bb0b  mov     rdi, rax
0x14001bb0e  test    rax, rax
0x14001bb11  jnz     loc_14001BC69
0x14001bb17  mov     eax, [rsp+58h+arg_30]
0x14001bb1e  lea     rbx, [rax+rax*8]
0x14001bb22  mov     rax, cs:gWfpGlobal
0x14001bb29  shl     rbx, 4
0x14001bb2d  add     rbx, [rax+1A8h]
0x14001bb34  mov     rcx, rbx
0x14001bb37  call    IsCalloutEntryAvailable
0x14001bb3c  mov     rdi, rax
0x14001bb3f  test    rax, rax
0x14001bb42  jnz     loc_14001BC69
0x14001bb48  mov     [rbx], r13d
0x14001bb4b  lea     ebp, [rax+1]
0x14001bb4e  mov     [rbx+4], ebp
0x14001bb51  cmp     r13d, 3
0x14001bb55  jnz     short loc_14001BB5D
0x14001bb57  mov     [rbx+30h], r15
0x14001bb5b  jmp     short loc_14001BB61
0x14001bb5d  mov     [rbx+18h], r15
0x14001bb61  mov     rax, [rsp+58h+arg_10]
0x14001bb66  xor     r13d, r13d
0x14001bb69  mov     [rbx+20h], rax
0x14001bb6d  mov     rax, [rsp+58h+arg_18]
0x14001bb72  mov     [rbx+28h], rax
0x14001bb76  mov     eax, [rsp+58h+arg_20]
0x14001bb7d  mov     [rbx+38h], eax
0x14001bb80  mov     al, [rsp+58h+arg_28]
0x14001bb87  mov     [rbx+76h], al
0x14001bb8a  test    r14, r14
0x14001bb8d  jz      short loc_14001BBA2
0x14001bb8f  mov     rcx, r14; Object
0x14001bb92  call    cs:__imp_ObfReferenceObject
0x14001bb99  nop     dword ptr [rax+rax+00h]
0x14001bb9e  mov     [rbx+68h], r14
0x14001bba2  movzx   eax, [rsp+58h+arg_40]
0x14001bbaa  mov     [rbx+74h], ax
0x14001bbae  cmp     [rbx+7Ch], r13d
0x14001bbb2  jbe     short loc_14001BBBE
0x14001bbb4  mov     eax, [rbx+38h]
0x14001bbb7  mov     r15b, bpl
0x14001bbba  test    al, 40h
0x14001bbbc  jz      short loc_14001BBC1
0x14001bbbe  mov     r15b, r13b
0x14001bbc1  cmp     [rbx+80h], r13d
0x14001bbc8  jbe     short loc_14001BBD6
0x14001bbca  test    dword ptr [rbx+38h], 100h
0x14001bbd1  mov     r14b, bpl
0x14001bbd4  jz      short loc_14001BBD9
0x14001bbd6  mov     r14b, r13b
0x14001bbd9  cmp     [rbx+84h], r13d
0x14001bbe0  jbe     short loc_14001BBEB
0x14001bbe2  test    dword ptr [rbx+38h], 200h
0x14001bbe9  jz      short loc_14001BBEE
0x14001bbeb  mov     bpl, r13b
0x14001bbee  cmp     [rbx+0Ch], r13b
0x14001bbf2  jz      short loc_14001BC22
0x14001bbf4  mov     eax, cs:dword_14009A098
0x14001bbfa  test    eax, eax
0x14001bbfc  jz      short loc_14001BC22
0x14001bbfe  mov     edx, 2
0x14001bc03  lea     rcx, dword_14009A098
0x14001bc0a  call    _tlgKeywordOn
0x14001bc0f  test    al, al
0x14001bc11  jz      short loc_14001BC22
0x14001bc13  mov     ecx, [rsp+58h+arg_30]
0x14001bc1a  mov     rdx, rbx
0x14001bc1d  call    WfpCalloutDiagTraceCalloutAddOrRegister
0x14001bc22  mov     [rbx+88h], rsi
0x14001bc29  lea     rdx, [rsp+58h+var_38]
0x14001bc2e  mov     rcx, cs:gWfpGlobal
0x14001bc35  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14001bc39  call    WfpReleaseFastWriteLock
0x14001bc3e  test    r15b, r15b
0x14001bc41  jz      short loc_14001BC48
0x14001bc43  call    KfdNotifyRscIncompatCalloutAdd
0x14001bc48  test    r14b, r14b
0x14001bc4b  jz      short loc_14001BC54
0x14001bc4d  xor     ecx, ecx
0x14001bc4f  call    KfdNotifyUsoIncompatCallout
0x14001bc54  test    bpl, bpl
0x14001bc57  jz      loc_14001BD02
0x14001bc5d  xor     ecx, ecx
0x14001bc5f  call    KfdNotifyUroIncompatCallout
0x14001bc64  jmp     loc_14001BD02
0x14001bc69  mov     rcx, cs:gWfpGlobal
0x14001bc70  lea     rdx, [rsp+58h+var_38]
0x14001bc75  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14001bc79  call    WfpReleaseFastWriteLock
0x14001bc7e  test    rsi, rsi
0x14001bc81  jz      short loc_14001BCF3
0x14001bc83  mov     rcx, [rsi+8]
0x14001bc87  call    cs:__imp_NdisNblTrackerDeregisterComponent
0x14001bc8e  nop     dword ptr [rax+rax+00h]
0x14001bc93  mov     rcx, [rsi]; IoWorkItem
0x14001bc96  call    cs:__imp_IoFreeWorkItem
0x14001bc9d  nop     dword ptr [rax+rax+00h]
0x14001bca2  mov     edx, 43706657h; Tag
0x14001bca7  mov     rcx, rsi; P
0x14001bcaa  call    cs:__imp_ExFreePoolWithTag
0x14001bcb1  nop     dword ptr [rax+rax+00h]
0x14001bcb6  jmp     loc_14001BAD9
0x14001bcbb  test    rsi, rsi
0x14001bcbe  jz      short loc_14001BCF3
0x14001bcc0  mov     rcx, [rsi+8]
0x14001bcc4  call    cs:__imp_NdisNblTrackerDeregisterComponent
0x14001bccb  nop     dword ptr [rax+rax+00h]
0x14001bcd0  mov     rcx, [rsi]; IoWorkItem
0x14001bcd3  call    cs:__imp_IoFreeWorkItem
0x14001bcda  nop     dword ptr [rax+rax+00h]
0x14001bcdf  mov     edx, 43706657h; Tag
0x14001bce4  mov     rcx, rsi; P
0x14001bce7  call    cs:__imp_ExFreePoolWithTag
0x14001bcee  nop     dword ptr [rax+rax+00h]
0x14001bcf3  lea     rdx, aFeregistercall; "FeRegisterCalloutEntry"
0x14001bcfa  mov     rcx, rdi
0x14001bcfd  call    WfpReportError
0x14001bd02  mov     rbx, [rsp+58h+arg_0]
0x14001bd07  mov     rax, rdi
0x14001bd0a  mov     rbp, [rsp+58h+arg_8]
0x14001bd0f  add     rsp, 30h
0x14001bd13  pop     r15
0x14001bd15  pop     r14
0x14001bd17  pop     r13
0x14001bd19  pop     rdi
0x14001bd1a  pop     rsi
0x14001bd1b  retn
```
