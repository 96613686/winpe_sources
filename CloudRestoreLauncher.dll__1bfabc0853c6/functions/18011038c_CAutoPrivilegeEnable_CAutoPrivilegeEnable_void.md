# CAutoPrivilegeEnable::~CAutoPrivilegeEnable(void)

- ea: `0x18011038c`
- end: `0x1801103da`
- name: `??1CAutoPrivilegeEnable@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CAutoPrivilegeEnable *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800b708c`
- `0x180125e79`

## callees

- `0x18011038c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801103c7`
- `KERNEL32!CloseHandle` at `0x1801103c7`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1801103b9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1801103b9`

## pseudocode

```c
void __fastcall CAutoPrivilegeEnable::~CAutoPrivilegeEnable(struct _TOKEN_PRIVILEGES *this)
{
  HANDLE *p_HighPart; // rbx

  p_HighPart = (HANDLE *)&this->Privileges[0].Luid.HighPart;
  if ( LOBYTE(this->PrivilegeCount) )
    AdjustTokenPrivileges(*p_HighPart, 0, this + 1, 0, 0, 0);
  if ( *p_HighPart )
  {
    CloseHandle(*p_HighPart);
    *p_HighPart = 0;
  }
}

```

## disassembly

```asm
0x18011038c  push    rbx
0x18011038e  sub     rsp, 30h
0x180110392  cmp     byte ptr [rcx], 0
0x180110395  lea     rbx, [rcx+8]
0x180110399  jz      short loc_1801103BF
0x18011039b  lea     r8, [rcx+10h]; NewState
0x18011039f  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1801103a8  mov     rcx, [rbx]; TokenHandle
0x1801103ab  xor     r9d, r9d; BufferLength
0x1801103ae  xor     edx, edx; DisableAllPrivileges
0x1801103b0  mov     [rsp+38h+PreviousState], 0; PreviousState
0x1801103b9  call    cs:__imp_AdjustTokenPrivileges
0x1801103bf  mov     rcx, [rbx]; hObject
0x1801103c2  test    rcx, rcx
0x1801103c5  jz      short loc_1801103D4
0x1801103c7  call    cs:__imp_CloseHandle
0x1801103cd  mov     qword ptr [rbx], 0
0x1801103d4  add     rsp, 30h
0x1801103d8  pop     rbx
0x1801103d9  retn
```
