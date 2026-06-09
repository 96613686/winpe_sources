# SiGetBiosSystemDisk

- ea: `0x1400254d0`
- end: `0x14002575e`
- name: `SiGetBiosSystemDisk`
- size: `654`
- prototype: `__int64 __fastcall(WCHAR **)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x140025764`

## callees

- `0x14001cbe4`
- `0x14001d3f8`
- `0x14001d47c`
- `0x14001d7cc`
- `0x1400254d0`
- `0x1400258a4`
- `0x140026650`

## import_xrefs

- `msvcrt!_snwscanf_s` at `0x14002558f`
- `msvcrt!_snwscanf_s` at `0x14002558f`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14002568e`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1400256eb`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14002568e`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1400256eb`
- `ntdll!RtlAllocateHeap` at `0x1400256bf`
- `ntdll!RtlAllocateHeap` at `0x1400256bf`
- `ntdll!RtlFreeHeap` at `0x1400255e6`
- `ntdll!RtlFreeHeap` at `0x140025731`
- `ntdll!RtlFreeHeap` at `0x1400255e6`
- `ntdll!RtlFreeHeap` at `0x140025731`
- `ntdll!NtClose` at `0x140025710`
- `ntdll!NtClose` at `0x140025710`
- `ntdll!RtlInitUnicodeString` at `0x14002567c`
- `ntdll!RtlInitUnicodeString` at `0x14002567c`

## pseudocode

```c
__int64 __fastcall SiGetBiosSystemDisk(WCHAR **a1)
{
  WCHAR *Heap; // rdi
  wchar_t *v3; // rbx
  __int64 v4; // rdx
  int v5; // eax
  bool v6; // zf
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  ULONG DataWritten; // [rsp+30h] [rbp-39h] BYREF
  HANDLE SymLinkObjHandle; // [rsp+38h] [rbp-31h]
  int v12; // [rsp+40h] [rbp-29h] BYREF
  int v13; // [rsp+44h] [rbp-25h] BYREF
  int v14; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  wchar_t *Buffer; // [rsp+60h] [rbp-9h] BYREF
  __int64 v17; // [rsp+68h] [rbp-1h]
  _QWORD v18[2]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v19; // [rsp+80h] [rbp+17h] BYREF
  __int128 v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+A0h] [rbp+37h]

  DataWritten = 0;
  DestinationString = 0;
  SymLinkObjHandle = 0;
  Heap = 0;
  Buffer = 0;
  v17 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v13 = 0;
  v12 = 0;
  memset(v18, 0, 12);
  v14 = 0;
  if ( !(unsigned __int8)SiIsWinPEBoot() )
    goto LABEL_15;
  if ( (int)SiGetBootDeviceNameFromRegistry(0, &Buffer) < 0 )
    goto LABEL_15;
  v3 = Buffer;
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  if ( _snwscanf_s(Buffer, v4 + 1, L"multi(%d)disk(%d)rdisk(%d)", &v12, &v13, &v14) != 3
    || v12
    || v13
    || v14
    || (int)SiTranslateSymbolicLink(L"\\ArcName\\multi(0)disk(0)rdisk(0)") < 0 )
  {
    goto LABEL_15;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  v21 = 0;
  memset(v18, 0, 12);
  v19 = 0;
  v20 = 0;
  v5 = SiIssueSynchronousIoctl(v17, 2954240, v18, 12, &v19, 40);
  v6 = v5 >= 0 ? HIDWORD(v20) == 7 : v5 == -1073741766;
  if ( !v6 || (v7 = SiOpenArcNameObject(L"\\ArcName\\multi(0)disk(0)rdisk(1)"), v7 == -1073740718) )
LABEL_15:
    v7 = SiOpenArcNameObject(L"\\ArcName\\multi(0)disk(0)rdisk(0)");
  if ( v7 >= 0 )
  {
    DataWritten = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v8 = NtQuerySymbolicLinkObject(SymLinkObjHandle, &DestinationString, &DataWritten);
    v7 = v8;
    if ( v8 == -1073741789 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataWritten + 2LL);
      if ( Heap )
      {
        DestinationString.MaximumLength = DataWritten;
        DestinationString.Buffer = Heap;
        v7 = NtQuerySymbolicLinkObject(SymLinkObjHandle, &DestinationString, 0);
        if ( v7 >= 0 )
        {
          Heap[(unsigned __int64)DestinationString.Length >> 1] = 0;
          *a1 = Heap;
        }
      }
      else
      {
        v7 = -1073741670;
      }
    }
    else if ( v8 >= 0 )
    {
      v7 = -1073741823;
    }
  }
  if ( SymLinkObjHandle )
    NtClose(SymLinkObjHandle);
  if ( v7 < 0 && Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400254d0  mov     [rsp-8+arg_8], rbx
0x1400254d5  mov     [rsp-8+arg_10], rdi
0x1400254da  push    rbp
0x1400254db  push    r14
0x1400254dd  push    r15
0x1400254df  lea     rbp, [rsp-47h]
0x1400254e4  sub     rsp, 0B0h
0x1400254eb  mov     rax, cs:__security_cookie
0x1400254f2  xor     rax, rsp
0x1400254f5  mov     [rbp+57h+var_18], rax
0x1400254f9  xor     r15d, r15d
0x1400254fc  xorps   xmm0, xmm0
0x1400254ff  xor     eax, eax
0x140025501  mov     [rbp+57h+DataWritten], r15d
0x140025505  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140025509  mov     [rbp+57h+SymLinkObjHandle], r15
0x14002550d  mov     edi, r15d
0x140025510  mov     [rbp+57h+Buffer], r15
0x140025514  mov     r14, rcx
0x140025517  mov     [rbp+57h+var_58], r15
0x14002551b  movups  [rbp+57h+var_40], xmm0
0x14002551f  mov     [rbp+57h+var_20], rax
0x140025523  movups  [rbp+57h+var_30], xmm0
0x140025527  mov     [rbp+57h+var_7C], r15d
0x14002552b  mov     [rbp+57h+var_80], r15d
0x14002552f  mov     [rbp+57h+var_50], rax
0x140025533  mov     [rbp+57h+var_48], eax
0x140025536  mov     [rbp+57h+var_78], r15d
0x14002553a  call    SiIsWinPEBoot
0x14002553f  test    al, al
0x140025541  jz      loc_140025658
0x140025547  lea     rdx, [rbp+57h+Buffer]
0x14002554b  xor     ecx, ecx
0x14002554d  call    SiGetBootDeviceNameFromRegistry
0x140025552  test    eax, eax
0x140025554  js      loc_140025658
0x14002555a  mov     rbx, [rbp+57h+Buffer]
0x14002555e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140025562  inc     rdx
0x140025565  cmp     [rbx+rdx*2], r15w
0x14002556a  jnz     short loc_140025562
0x14002556c  lea     rax, [rbp+57h+var_78]
0x140025570  inc     rdx; BufferCount
0x140025573  mov     [rsp+0C0h+var_98], rax
0x140025578  lea     r9, [rbp+57h+var_80]
0x14002557c  lea     rax, [rbp+57h+var_7C]
0x140025580  mov     rcx, rbx; Buffer
0x140025583  lea     r8, aMultiDDiskDRdi; "multi(%d)disk(%d)rdisk(%d)"
0x14002558a  mov     [rsp+0C0h+var_A0], rax
0x14002558f  call    cs:__imp__snwscanf_s
0x140025595  cmp     eax, 3
0x140025598  jnz     loc_140025658
0x14002559e  cmp     [rbp+57h+var_80], r15d
0x1400255a2  jnz     loc_140025658
0x1400255a8  cmp     [rbp+57h+var_7C], r15d
0x1400255ac  jnz     loc_140025658
0x1400255b2  cmp     [rbp+57h+var_78], r15d
0x1400255b6  jnz     loc_140025658
0x1400255bc  lea     rdx, [rbp+57h+var_58]
0x1400255c0  lea     rcx, aArcnameMulti0D_0; "\\ArcName\\multi(0)disk(0)rdisk(0)"
0x1400255c7  call    SiTranslateSymbolicLink
0x1400255cc  test    eax, eax
0x1400255ce  js      loc_140025658
0x1400255d4  mov     rcx, gs:60h
0x1400255dd  mov     r8, rbx; P
0x1400255e0  xor     edx, edx; Flags
0x1400255e2  mov     rcx, [rcx+30h]; HeapHandle
0x1400255e6  call    cs:__imp_RtlFreeHeap
0x1400255ec  mov     rcx, [rbp+57h+var_58]
0x1400255f0  lea     r8, [rbp+57h+var_50]
0x1400255f4  xor     eax, eax
0x1400255f6  mov     dword ptr [rsp+0C0h+var_98], 28h ; '('
0x1400255fe  xorps   xmm0, xmm0
0x140025601  mov     [rbp+57h+var_20], rax
0x140025605  lea     rax, [rbp+57h+var_40]
0x140025609  mov     [rbp+57h+var_50+4], r15
0x14002560d  mov     r9d, 0Ch
0x140025613  mov     [rsp+0C0h+var_A0], rax
0x140025618  mov     edx, 2D1400h
0x14002561d  mov     dword ptr [rbp+57h+var_50], r15d
0x140025621  movups  [rbp+57h+var_40], xmm0
0x140025625  movups  [rbp+57h+var_30], xmm0
0x140025629  call    SiIssueSynchronousIoctl
0x14002562e  test    eax, eax
0x140025630  jns     short loc_140025639
0x140025632  cmp     eax, 0C000003Ah
0x140025637  jmp     short loc_14002563D
0x140025639  cmp     dword ptr [rbp+57h+var_30+0Ch], 7
0x14002563d  jnz     short loc_140025658
0x14002563f  lea     rdx, [rbp+57h+SymLinkObjHandle]
0x140025643  lea     rcx, aArcnameMulti0D; "\\ArcName\\multi(0)disk(0)rdisk(1)"
0x14002564a  call    SiOpenArcNameObject
0x14002564f  mov     ebx, eax
0x140025651  cmp     eax, 0C0000452h
0x140025656  jnz     short loc_14002566A
0x140025658  lea     rdx, [rbp+57h+SymLinkObjHandle]
0x14002565c  lea     rcx, aArcnameMulti0D_0; "\\ArcName\\multi(0)disk(0)rdisk(0)"
0x140025663  call    SiOpenArcNameObject
0x140025668  mov     ebx, eax
0x14002566a  test    ebx, ebx
0x14002566c  js      loc_140025706
0x140025672  xor     edx, edx; SourceString
0x140025674  mov     [rbp+57h+DataWritten], r15d
0x140025678  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002567c  call    cs:__imp_RtlInitUnicodeString
0x140025682  mov     rcx, [rbp+57h+SymLinkObjHandle]; SymLinkObjHandle
0x140025686  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x14002568a  lea     rdx, [rbp+57h+DestinationString]; LinkTarget
0x14002568e  call    cs:__imp_NtQuerySymbolicLinkObject
0x140025694  mov     ebx, eax
0x140025696  cmp     eax, 0C0000023h
0x14002569b  jz      short loc_1400256A8
0x14002569d  test    eax, eax
0x14002569f  js      short loc_140025706
0x1400256a1  mov     ebx, 0C0000001h
0x1400256a6  jmp     short loc_140025706
0x1400256a8  mov     rcx, gs:60h
0x1400256b1  xor     edx, edx; Flags
0x1400256b3  mov     r8d, [rbp+57h+DataWritten]
0x1400256b7  add     r8, 2; Size
0x1400256bb  mov     rcx, [rcx+30h]; HeapHandle
0x1400256bf  call    cs:__imp_RtlAllocateHeap
0x1400256c5  mov     rdi, rax
0x1400256c8  test    rax, rax
0x1400256cb  jnz     short loc_1400256D4
0x1400256cd  mov     ebx, 0C000009Ah
0x1400256d2  jmp     short loc_140025706
0x1400256d4  movzx   eax, word ptr [rbp+57h+DataWritten]
0x1400256d8  lea     rdx, [rbp+57h+DestinationString]; LinkTarget
0x1400256dc  mov     rcx, [rbp+57h+SymLinkObjHandle]; SymLinkObjHandle
0x1400256e0  xor     r8d, r8d; DataWritten
0x1400256e3  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x1400256e7  mov     [rbp+57h+DestinationString.Buffer], rdi
0x1400256eb  call    cs:__imp_NtQuerySymbolicLinkObject
0x1400256f1  mov     ebx, eax
0x1400256f3  test    eax, eax
0x1400256f5  js      short loc_140025706
0x1400256f7  movzx   edx, [rbp+57h+DestinationString.Length]
0x1400256fb  shr     rdx, 1
0x1400256fe  mov     [rdi+rdx*2], r15w
0x140025703  mov     [r14], rdi
0x140025706  cmp     [rbp+57h+SymLinkObjHandle], r15
0x14002570a  jz      short loc_140025716
0x14002570c  mov     rcx, [rbp+57h+SymLinkObjHandle]; Handle
0x140025710  call    cs:__imp_NtClose
0x140025716  test    ebx, ebx
0x140025718  jns     short loc_140025737
0x14002571a  test    rdi, rdi
0x14002571d  jz      short loc_140025737
0x14002571f  mov     rcx, gs:60h
0x140025728  mov     r8, rdi; P
0x14002572b  xor     edx, edx; Flags
0x14002572d  mov     rcx, [rcx+30h]; HeapHandle
0x140025731  call    cs:__imp_RtlFreeHeap
0x140025737  mov     eax, ebx
0x140025739  mov     rcx, [rbp+57h+var_18]
0x14002573d  xor     rcx, rsp; StackCookie
0x140025740  call    __security_check_cookie
0x140025745  lea     r11, [rsp+0C0h+var_10]
0x14002574d  mov     rbx, [r11+28h]
0x140025751  mov     rdi, [r11+30h]
0x140025755  mov     rsp, r11
0x140025758  pop     r15
0x14002575a  pop     r14
0x14002575c  pop     rbp
0x14002575d  retn
```
