# UnionFs::Utils::QueryProcessImageFileName(utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>> &,UnionFs::StackEventTracer &,_KPROCESS *)

- ea: `0x1400756ac`
- end: `0x140075994`
- name: `?QueryProcessImageFileName@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@AEAVStackEventTracer@2@PEAU_KPROCESS@@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14006f70c`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x1400756ac`

## import_xrefs

- `ntoskrnl!ZwQueryInformationProcess` at `0x140075798`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140075798`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400756ea`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400756ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075800`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075955`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075800`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075901`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075955`
- `ntoskrnl!ExAllocatePool2` at `0x1400757e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400757e2`
- `ntoskrnl!ZwClose` at `0x14007575d`
- `ntoskrnl!ZwClose` at `0x1400758d4`
- `ntoskrnl!ZwClose` at `0x140075916`
- `ntoskrnl!ZwClose` at `0x14007596a`
- `ntoskrnl!ZwClose` at `0x14007575d`
- `ntoskrnl!ZwClose` at `0x1400758d4`
- `ntoskrnl!ZwClose` at `0x140075916`
- `ntoskrnl!ZwClose` at `0x14007596a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007571b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007571b`

## string_xrefs

- `0x14007572d`: `API: Opening process handle`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::QueryProcessImageFileName(void **a1, int a2, __int64 a3)
{
  void *v4; // rcx
  PEPROCESS CurrentProcess; // rax
  NTSTATUS v7; // ebx
  _WORD *v9; // rbx
  ULONG v10; // r9d
  int i; // r15d
  NTSTATUS InformationProcess; // edi
  __int64 v13; // rdx
  __int64 Pool2; // rax
  void *v15; // rcx
  __int64 v16; // r8
  void *v17; // rcx
  const char *AccessMode; // [rsp+28h] [rbp-18h]
  HANDLE ProcessHandle; // [rsp+80h] [rbp+40h] BYREF
  __int64 ReturnLength; // [rsp+90h] [rbp+50h] BYREF

  ReturnLength = a3;
  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  CurrentProcess = IoGetCurrentProcess();
  ProcessHandle = 0;
  v7 = ObOpenObjectByPointer(CurrentProcess, 0x200u, 0, 0, 0, 0, &ProcessHandle);
  if ( v7 >= 0 )
  {
    v9 = 0;
    LODWORD(ReturnLength) = 0;
    v10 = 0;
    for ( i = 0; ; i = 1 )
    {
      InformationProcess = ZwQueryInformationProcess(
                             ProcessHandle,
                             ProcessImageFileName,
                             v9,
                             v10,
                             (PULONG)&ReturnLength);
      if ( i )
        break;
      if ( (int)(InformationProcess + 0x80000000) >= 0 && InformationProcess != -1073741820 )
      {
        v16 = 0x4E300212460LL;
LABEL_24:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)InformationProcess,
          a2,
          (struct UnionFs::StackEventTracer *)v16,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "API: Querying process image file name",
          AccessMode);
        goto LABEL_25;
      }
      if ( (unsigned int)ReturnLength < 0x10 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000001LL,
          a2,
          (struct UnionFs::StackEventTracer *)0x4E50021246ELL,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "ORIGIN: Invalid buffer size for process image file name",
          AccessMode);
        if ( v9 )
LABEL_38:
          ExFreePoolWithTag(v9, 0);
        if ( ProcessHandle )
          ZwClose(ProcessHandle);
        return 3221225473LL;
      }
      v13 = (unsigned int)ReturnLength;
      if ( !(_DWORD)ReturnLength )
        v13 = 1;
      Pool2 = ExAllocatePool2(256, v13, 1852261973);
      if ( !Pool2 )
      {
        InformationProcess = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          a2,
          (struct UnionFs::StackEventTracer *)0x4E600212477LL,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "ORIGIN: Allocating image file name buffer",
          AccessMode);
LABEL_25:
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
        if ( ProcessHandle )
          ZwClose(ProcessHandle);
        return (unsigned int)InformationProcess;
      }
      v15 = v9;
      v9 = (_WORD *)Pool2;
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      v10 = ReturnLength;
    }
    if ( InformationProcess < 0 )
    {
      v16 = 0x4E100212450LL;
      goto LABEL_24;
    }
    if ( !*v9 || (*v9 & 1) != 0 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000001LL,
        a2,
        (struct UnionFs::StackEventTracer *)0x4E200212457LL,
        (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
        "ORIGIN: Invalid image file name",
        AccessMode);
      goto LABEL_38;
    }
    v17 = *a1;
    *a1 = v9;
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    if ( ProcessHandle )
      ZwClose(ProcessHandle);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v7,
      a2,
      (struct UnionFs::StackEventTracer *)0x4E00021243ELL,
      (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
      "API: Opening process handle",
      AccessMode);
    if ( ProcessHandle )
      ZwClose(ProcessHandle);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1400756ac  mov     [rsp-38h+arg_8], rbx
0x1400756b1  mov     [rsp-38h+ReturnLength], r8
0x1400756b6  push    rbp
0x1400756b7  push    rsi
0x1400756b8  push    rdi
0x1400756b9  push    r12
0x1400756bb  push    r13
0x1400756bd  push    r14
0x1400756bf  push    r15
0x1400756c1  mov     rbp, rsp
0x1400756c4  sub     rsp, 40h
0x1400756c8  mov     rsi, rcx
0x1400756cb  xor     r12d, r12d
0x1400756ce  mov     rcx, [rcx]; P
0x1400756d1  mov     r14, rdx
0x1400756d4  mov     [rsi], r12
0x1400756d7  test    rcx, rcx
0x1400756da  jz      short loc_1400756EA
0x1400756dc  xor     edx, edx; Tag
0x1400756de  call    cs:__imp_ExFreePoolWithTag
0x1400756e5  nop     dword ptr [rax+rax+00h]
0x1400756ea  call    cs:__imp_IoGetCurrentProcess
0x1400756f1  nop     dword ptr [rax+rax+00h]
0x1400756f6  lea     rcx, [rbp+ProcessHandle]
0x1400756fa  mov     [rbp+ProcessHandle], r12
0x1400756fe  mov     [rsp+40h+Handle], rcx; Handle
0x140075703  xor     r9d, r9d; DesiredAccess
0x140075706  mov     byte ptr [rsp+40h+AccessMode], r12b; char *
0x14007570b  mov     rcx, rax; Object
0x14007570e  xor     r8d, r8d; PassedAccessState
0x140075711  mov     [rsp+40h+ObjectType], r12; ObjectType
0x140075716  mov     edx, 200h; HandleAttributes
0x14007571b  call    cs:__imp_ObOpenObjectByPointer
0x140075722  nop     dword ptr [rax+rax+00h]
0x140075727  mov     ebx, eax
0x140075729  test    eax, eax
0x14007572b  jns     short loc_140075770
0x14007572d  lea     rax, aApiOpeningProc; "API: Opening process handle"
0x140075734  mov     r8, 4E00021243Eh; struct UnionFs::StackEventTracer *
0x14007573e  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x140075745  mov     [rsp+40h+ObjectType], rax; char *
0x14007574a  mov     rdx, r14; int
0x14007574d  mov     ecx, ebx; this
0x14007574f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075754  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075758  test    rcx, rcx
0x14007575b  jz      short loc_140075769
0x14007575d  call    cs:__imp_ZwClose
0x140075764  nop     dword ptr [rax+rax+00h]
0x140075769  mov     eax, ebx
0x14007576b  jmp     loc_14007597B
0x140075770  mov     rbx, r12
0x140075773  mov     dword ptr [rbp+ReturnLength], r12d
0x140075777  mov     r9d, r12d; ProcessInformationLength
0x14007577a  mov     r15d, r12d
0x14007577d  mov     r13d, 1
0x140075783  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140075787  lea     rax, [rbp+ReturnLength]
0x14007578b  mov     r8, rbx; ProcessInformation
0x14007578e  mov     [rsp+40h+ObjectType], rax; ReturnLength
0x140075793  mov     edx, 1Bh; ProcessInformationClass
0x140075798  call    cs:__imp_ZwQueryInformationProcess
0x14007579f  nop     dword ptr [rax+rax+00h]
0x1400757a4  mov     edi, eax
0x1400757a6  test    r15d, r15d
0x1400757a9  jnz     loc_14007588A
0x1400757af  mov     eax, 80000000h
0x1400757b4  lea     ecx, [rdi+rax]
0x1400757b7  test    eax, ecx
0x1400757b9  jnz     short loc_1400757C3
0x1400757bb  cmp     edi, 0C0000004h
0x1400757c1  jnz     short loc_140075818
0x1400757c3  cmp     dword ptr [rbp+ReturnLength], 10h
0x1400757c7  jb      loc_140075852
0x1400757cd  mov     edx, dword ptr [rbp+ReturnLength]
0x1400757d0  mov     ecx, 100h
0x1400757d5  test    rdx, rdx
0x1400757d8  mov     r8d, 6E674655h
0x1400757de  cmovz   rdx, r13
0x1400757e2  call    cs:__imp_ExAllocatePool2
0x1400757e9  nop     dword ptr [rax+rax+00h]
0x1400757ee  test    rax, rax
0x1400757f1  jz      short loc_140075824
0x1400757f3  mov     rcx, rbx; P
0x1400757f6  mov     rbx, rax
0x1400757f9  test    rcx, rcx
0x1400757fc  jz      short loc_14007580C
0x1400757fe  xor     edx, edx; Tag
0x140075800  call    cs:__imp_ExFreePoolWithTag
0x140075807  nop     dword ptr [rax+rax+00h]
0x14007580c  mov     r9d, dword ptr [rbp+ReturnLength]
0x140075810  mov     r15d, r13d
0x140075813  jmp     loc_140075783
0x140075818  mov     r8, 4E300212460h
0x140075822  jmp     short loc_140075898
0x140075824  lea     rax, aOriginAllocati_27; "ORIGIN: Allocating image file name buff"...
0x14007582b  mov     edi, 0C000009Ah
0x140075830  mov     ecx, edi; this
0x140075832  mov     [rsp+40h+ObjectType], rax; char *
0x140075837  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007583e  mov     r8, 4E600212477h; struct UnionFs::StackEventTracer *
0x140075848  mov     rdx, r14; int
0x14007584b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075850  jmp     short loc_1400758B5
0x140075852  lea     rax, aOriginInvalidB; "ORIGIN: Invalid buffer size for process"...
0x140075859  mov     r8, 4E50021246Eh; struct UnionFs::StackEventTracer *
0x140075863  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007586a  mov     [rsp+40h+ObjectType], rax; char *
0x14007586f  mov     rdx, r14; int
0x140075872  mov     ecx, 0C0000001h; this
0x140075877  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007587c  test    rbx, rbx
0x14007587f  jz      loc_140075961
0x140075885  jmp     loc_140075950
0x14007588a  test    edi, edi
0x14007588c  jns     short loc_1400758E7
0x14007588e  mov     r8, 4E100212450h; struct UnionFs::StackEventTracer *
0x140075898  lea     rax, aApiQueryingPro; "API: Querying process image file name"
0x14007589f  mov     rdx, r14; int
0x1400758a2  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x1400758a9  mov     [rsp+40h+ObjectType], rax; char *
0x1400758ae  mov     ecx, edi; this
0x1400758b0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400758b5  test    rbx, rbx
0x1400758b8  jz      short loc_1400758CB
0x1400758ba  xor     edx, edx; Tag
0x1400758bc  mov     rcx, rbx; P
0x1400758bf  call    cs:__imp_ExFreePoolWithTag
0x1400758c6  nop     dword ptr [rax+rax+00h]
0x1400758cb  mov     rcx, [rbp+ProcessHandle]; Handle
0x1400758cf  test    rcx, rcx
0x1400758d2  jz      short loc_1400758E0
0x1400758d4  call    cs:__imp_ZwClose
0x1400758db  nop     dword ptr [rax+rax+00h]
0x1400758e0  mov     eax, edi
0x1400758e2  jmp     loc_14007597B
0x1400758e7  movzx   eax, word ptr [rbx]
0x1400758ea  test    ax, ax
0x1400758ed  jz      short loc_140075926
0x1400758ef  test    r13b, al
0x1400758f2  jnz     short loc_140075926
0x1400758f4  mov     rcx, [rsi]; P
0x1400758f7  mov     [rsi], rbx
0x1400758fa  test    rcx, rcx
0x1400758fd  jz      short loc_14007590D
0x1400758ff  xor     edx, edx; Tag
0x140075901  call    cs:__imp_ExFreePoolWithTag
0x140075908  nop     dword ptr [rax+rax+00h]
0x14007590d  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075911  test    rcx, rcx
0x140075914  jz      short loc_140075922
0x140075916  call    cs:__imp_ZwClose
0x14007591d  nop     dword ptr [rax+rax+00h]
0x140075922  xor     eax, eax
0x140075924  jmp     short loc_14007597B
0x140075926  lea     rax, aOriginInvalidI; "ORIGIN: Invalid image file name"
0x14007592d  mov     r8, 4E200212457h; struct UnionFs::StackEventTracer *
0x140075937  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007593e  mov     [rsp+40h+ObjectType], rax; char *
0x140075943  mov     rdx, r14; int
0x140075946  mov     ecx, 0C0000001h; this
0x14007594b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075950  xor     edx, edx; Tag
0x140075952  mov     rcx, rbx; P
0x140075955  call    cs:__imp_ExFreePoolWithTag
0x14007595c  nop     dword ptr [rax+rax+00h]
0x140075961  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075965  test    rcx, rcx
0x140075968  jz      short loc_140075976
0x14007596a  call    cs:__imp_ZwClose
0x140075971  nop     dword ptr [rax+rax+00h]
0x140075976  mov     eax, 0C0000001h
0x14007597b  mov     rbx, [rsp+40h+arg_8]
0x140075983  add     rsp, 40h
0x140075987  pop     r15
0x140075989  pop     r14
0x14007598b  pop     r13
0x14007598d  pop     r12
0x14007598f  pop     rdi
0x140075990  pop     rsi
0x140075991  pop     rbp
0x140075992  retn
```
