# AhgGetFileExeType

- ea: `0x180011d60`
- end: `0x180011e8b`
- name: `AhgGetFileExeType`
- size: `299`
- prototype: `__int64 __fastcall(_WORD *, BOOL *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010d10`

## callees

- `0x180011d60`
- `0x180015220`
- `0x18001623a`

## import_xrefs

- `ntdll!NtQuerySection` at `0x180011e20`
- `ntdll!NtQuerySection` at `0x180011e20`
- `ntdll!RtlNtStatusToDosError` at `0x180011dcc`
- `ntdll!RtlNtStatusToDosError` at `0x180011e2c`
- `ntdll!RtlNtStatusToDosError` at `0x180011dcc`
- `ntdll!RtlNtStatusToDosError` at `0x180011e2c`
- `ntdll!NtCreateSection` at `0x180011dc0`
- `ntdll!NtCreateSection` at `0x180011dc0`
- `ntdll!NtClose` at `0x180011e76`
- `ntdll!NtClose` at `0x180011e76`

## string_xrefs

- `0x180011ddf`: `Failed to create section [%d]`

## pseudocode

```c
__int64 __fastcall AhgGetFileExeType(_WORD *a1, BOOL *a2, void *a3)
{
  int v6; // eax
  ULONG v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  int Section; // eax
  ULONG v12; // eax
  BOOL v13; // eax
  _BYTE SectionInformation[48]; // [rsp+40h] [rbp-68h] BYREF
  __int16 v16; // [rsp+70h] [rbp-38h]
  char v17; // [rsp+73h] [rbp-35h]
  void *SectionHandle; // [rsp+B0h] [rbp+8h] BYREF

  SectionHandle = 0;
  memset_0(SectionInformation, 0, 0x40u);
  *a1 = 0;
  *a2 = 0;
  v6 = NtCreateSection(&SectionHandle, 1u, 0, 0, 2u, 0x11000000u, a3);
  if ( v6 < 0 )
  {
    v7 = RtlNtStatusToDosError(v6);
    if ( v7 == 193 )
      goto LABEL_10;
    v8 = "Failed to create section [%d]";
    v9 = 150;
    v10 = 1;
    goto LABEL_4;
  }
  Section = NtQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
  if ( Section < 0 )
  {
    v12 = RtlNtStatusToDosError(Section);
    v8 = "Failed to get the section information [%d]";
    v9 = 163;
    v7 = v12;
    v10 = 2;
LABEL_4:
    AslLogCallPrintf(v10, "AhgGetFileExeType", v9, v8);
    goto LABEL_10;
  }
  v13 = 0;
  if ( v16 == 332 )
    v13 = (v17 & 1) != 0;
  *a1 = v16;
  v7 = 0;
  *a2 = v13;
LABEL_10:
  if ( SectionHandle )
    NtClose(SectionHandle);
  return v7;
}

```

## disassembly

```asm
0x180011d60  mov     rax, rsp
0x180011d63  push    rbx
0x180011d64  push    rsi
0x180011d65  push    rdi
0x180011d66  push    r14
0x180011d68  sub     rsp, 88h
0x180011d6f  mov     rdi, rdx
0x180011d72  mov     qword ptr [rax+8], 0
0x180011d7a  xor     edx, edx; Val
0x180011d7c  mov     rbx, r8
0x180011d7f  mov     rsi, rcx
0x180011d82  lea     rcx, [rax-68h]; void *
0x180011d86  lea     r8d, [rdx+40h]; Size
0x180011d8a  call    memset_0
0x180011d8f  xor     eax, eax
0x180011d91  mov     [rsp+0A8h+FileHandle], rbx; FileHandle
0x180011d96  mov     [rsi], ax
0x180011d99  lea     rcx, [rsp+0A8h+SectionHandle]; SectionHandle
0x180011da1  mov     [rsp+0A8h+AllocationAttributes], 11000000h; AllocationAttributes
0x180011da9  xor     r9d, r9d; MaximumSize
0x180011dac  xor     r8d, r8d; ObjectAttributes
0x180011daf  mov     [rdi], eax
0x180011db1  lea     r14d, [rax+1]
0x180011db5  mov     [rsp+0A8h+SectionPageProtection], 2; SectionPageProtection
0x180011dbd  mov     edx, r14d; DesiredAccess
0x180011dc0  call    cs:__imp_NtCreateSection
0x180011dc6  test    eax, eax
0x180011dc8  jns     short loc_180011E01
0x180011dca  mov     ecx, eax; Status
0x180011dcc  call    cs:__imp_RtlNtStatusToDosError
0x180011dd2  mov     ebx, eax
0x180011dd4  cmp     eax, 0C1h
0x180011dd9  jz      loc_180011E69
0x180011ddf  lea     r9, aFailedToCreate_0; "Failed to create section [%d]"
0x180011de6  mov     r8d, 96h
0x180011dec  mov     ecx, r14d
0x180011def  lea     rdx, aAhggetfileexet; "AhgGetFileExeType"
0x180011df6  mov     [rsp+0A8h+SectionPageProtection], eax
0x180011dfa  call    AslLogCallPrintf
0x180011dff  jmp     short loc_180011E69
0x180011e01  mov     rcx, [rsp+0A8h+SectionHandle]; SectionHandle
0x180011e09  lea     r8, [rsp+0A8h+SectionInformation]; SectionInformation
0x180011e0e  mov     r9d, 40h ; '@'; Length
0x180011e14  mov     qword ptr [rsp+0A8h+SectionPageProtection], 0; ResultLength
0x180011e1d  mov     edx, r14d; SectionInformationClass
0x180011e20  call    cs:__imp_NtQuerySection
0x180011e26  test    eax, eax
0x180011e28  jns     short loc_180011E48
0x180011e2a  mov     ecx, eax; Status
0x180011e2c  call    cs:__imp_RtlNtStatusToDosError
0x180011e32  lea     r9, aFailedToGetThe_1; "Failed to get the section information ["...
0x180011e39  mov     r8d, 0A3h
0x180011e3f  mov     ebx, eax
0x180011e41  mov     ecx, 2
0x180011e46  jmp     short loc_180011DEF
0x180011e48  movzx   ecx, [rsp+0A8h+var_38]
0x180011e4d  xor     eax, eax
0x180011e4f  mov     edx, 14Ch
0x180011e54  cmp     cx, dx
0x180011e57  jnz     short loc_180011E62
0x180011e59  test    [rsp+0A8h+var_35], r14b
0x180011e5e  cmovnz  eax, r14d
0x180011e62  mov     [rsi], cx
0x180011e65  xor     ebx, ebx
0x180011e67  mov     [rdi], eax
0x180011e69  mov     rcx, [rsp+0A8h+SectionHandle]; Handle
0x180011e71  test    rcx, rcx
0x180011e74  jz      short loc_180011E7C
0x180011e76  call    cs:__imp_NtClose
0x180011e7c  mov     eax, ebx
0x180011e7e  add     rsp, 88h
0x180011e85  pop     r14
0x180011e87  pop     rdi
0x180011e88  pop     rsi
0x180011e89  pop     rbx
0x180011e8a  retn
```
