# BipReadRegSid

- ea: `0x1800457ac`
- end: `0x18004594c`
- name: `BipReadRegSid`
- size: `416`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName, PSID DestinationSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004786c`

## callees

- `0x180026080`
- `0x1800457ac`
- `0x180049844`
- `0x18004df58`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180045801`
- `ntdll!NtQueryValueKey` at `0x18004587d`
- `ntdll!NtQueryValueKey` at `0x180045801`
- `ntdll!NtQueryValueKey` at `0x18004587d`
- `ntdll!RtlFreeHeap` at `0x1800458b8`
- `ntdll!RtlFreeHeap` at `0x1800458b8`
- `ntdll!RtlAllocateHeap` at `0x18004584e`
- `ntdll!RtlAllocateHeap` at `0x18004584e`
- `ntdll!RtlValidSid` at `0x180045899`
- `ntdll!RtlValidSid` at `0x180045899`
- `ntdll!RtlCopySid` at `0x18004593f`
- `ntdll!RtlCopySid` at `0x18004593f`

## pseudocode

```c
__int64 __fastcall BipReadRegSid(HANDLE KeyHandle, PUNICODE_STRING ValueName, PSID DestinationSid)
{
  unsigned int v6; // ebx
  _DWORD *Heap; // rax
  _DWORD *v9; // rdi
  NTSTATUS v10; // eax
  ULONG ResultLength; // [rsp+68h] [rbp+20h] BYREF

  ResultLength = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids,
      ValueName->Buffer);
  v6 = NtQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v6 == -1073741789 )
  {
    Heap = RtlAllocateHeap(BipHeap, 0, ResultLength);
    v9 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    v10 = NtQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, Heap, ResultLength, &ResultLength);
    v6 = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -1073741772
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids,
          (unsigned int)v10);
      }
      goto LABEL_12;
    }
    if ( v9[1] != 3 )
      goto LABEL_11;
    if ( v9[2] > 0x44u )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
      v6 = -1073741789;
      goto LABEL_12;
    }
    if ( RtlValidSid(v9 + 3) )
      v6 = RtlCopySid(0x44u, DestinationSid, v9 + 3);
    else
LABEL_11:
      v6 = -1073741811;
LABEL_12:
    RtlFreeHeap(BipHeap, 0, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x1800457ac  mov     [rsp+arg_0], rbx
0x1800457b1  mov     [rsp+arg_8], rbp
0x1800457b6  push    rsi
0x1800457b7  push    rdi
0x1800457b8  push    r14
0x1800457ba  sub     rsp, 30h
0x1800457be  mov     r14, r8
0x1800457c1  mov     [rsp+48h+arg_18], 0
0x1800457c9  mov     rsi, rdx
0x1800457cc  mov     rbp, rcx
0x1800457cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800457d6  test    byte ptr [rcx+1Ch], 8
0x1800457da  jz      short loc_1800457E2
0x1800457dc  cmp     byte ptr [rcx+19h], 5
0x1800457e0  jnb     short loc_180045825
0x1800457e2  xor     r9d, r9d; KeyValueInformation
0x1800457e5  lea     rax, [rsp+48h+arg_18]
0x1800457ea  mov     [rsp+48h+ResultLength], rax; ResultLength
0x1800457ef  mov     rdx, rsi; ValueName
0x1800457f2  mov     rcx, rbp; KeyHandle
0x1800457f5  mov     [rsp+48h+Length], 0; Length
0x1800457fd  lea     r8d, [r9+2]; KeyValueInformationClass
0x180045801  call    cs:__imp_NtQueryValueKey
0x180045807  mov     ebx, eax
0x180045809  cmp     eax, 0C0000023h
0x18004580e  jz      short loc_180045840
0x180045810  mov     rbp, [rsp+48h+arg_8]
0x180045815  mov     eax, ebx
0x180045817  mov     rbx, [rsp+48h+arg_0]
0x18004581c  add     rsp, 30h
0x180045820  pop     r14
0x180045822  pop     rdi
0x180045823  pop     rsi
0x180045824  retn
0x180045825  mov     r9, [rsi+8]
0x180045829  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x180045830  mov     rcx, [rcx+10h]
0x180045834  mov     edx, 1Ah
0x180045839  call    WPP_SF_S
0x18004583e  jmp     short loc_1800457E2
0x180045840  mov     r8d, [rsp+48h+arg_18]; Size
0x180045845  xor     edx, edx; Flags
0x180045847  mov     rcx, cs:BipHeap; HeapHandle
0x18004584e  call    cs:__imp_RtlAllocateHeap
0x180045854  mov     rdi, rax
0x180045857  test    rax, rax
0x18004585a  jz      short loc_1800458C3
0x18004585c  lea     rax, [rsp+48h+arg_18]
0x180045861  mov     r9, rdi; KeyValueInformation
0x180045864  mov     [rsp+48h+ResultLength], rax; ResultLength
0x180045869  mov     r8d, 2; KeyValueInformationClass
0x18004586f  mov     eax, [rsp+48h+arg_18]
0x180045873  mov     rdx, rsi; ValueName
0x180045876  mov     rcx, rbp; KeyHandle
0x180045879  mov     [rsp+48h+Length], eax; Length
0x18004587d  call    cs:__imp_NtQueryValueKey
0x180045883  mov     ebx, eax
0x180045885  test    eax, eax
0x180045887  js      short loc_1800458CD
0x180045889  cmp     dword ptr [rdi+4], 3
0x18004588d  jnz     short loc_1800458A7
0x18004588f  cmp     dword ptr [rdi+8], 44h ; 'D'
0x180045893  ja      short loc_180045901
0x180045895  lea     rcx, [rdi+0Ch]; Sid
0x180045899  call    cs:__imp_RtlValidSid
0x18004589f  test    al, al
0x1800458a1  jnz     loc_180045933
0x1800458a7  mov     ebx, 0C000000Dh
0x1800458ac  mov     rcx, cs:BipHeap; HeapHandle
0x1800458b3  mov     r8, rdi; P
0x1800458b6  xor     edx, edx; Flags
0x1800458b8  call    cs:__imp_RtlFreeHeap
0x1800458be  jmp     loc_180045810
0x1800458c3  mov     ebx, 0C0000017h
0x1800458c8  jmp     loc_180045810
0x1800458cd  cmp     eax, 0C0000034h
0x1800458d2  jz      short loc_1800458AC
0x1800458d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800458db  test    byte ptr [rcx+1Ch], 8
0x1800458df  jz      short loc_1800458AC
0x1800458e1  cmp     byte ptr [rcx+19h], 2
0x1800458e5  jb      short loc_1800458AC
0x1800458e7  mov     rcx, [rcx+10h]
0x1800458eb  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x1800458f2  mov     edx, 1Bh
0x1800458f7  mov     r9d, eax
0x1800458fa  call    WPP_SF_d
0x1800458ff  jmp     short loc_1800458AC
0x180045901  mov     rcx, cs:WPP_GLOBAL_Control
0x180045908  test    byte ptr [rcx+1Ch], 8
0x18004590c  jz      short loc_180045929
0x18004590e  cmp     byte ptr [rcx+19h], 2
0x180045912  jb      short loc_180045929
0x180045914  mov     rcx, [rcx+10h]
0x180045918  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18004591f  mov     edx, 1Ch
0x180045924  call    WPP_SF_
0x180045929  mov     ebx, 0C0000023h
0x18004592e  jmp     loc_1800458AC
0x180045933  lea     r8, [rdi+0Ch]; SourceSid
0x180045937  mov     rdx, r14; DestinationSid
0x18004593a  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18004593f  call    cs:__imp_RtlCopySid
0x180045945  mov     ebx, eax
0x180045947  jmp     loc_1800458AC
```
