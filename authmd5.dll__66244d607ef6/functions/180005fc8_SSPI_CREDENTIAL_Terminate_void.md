# SSPI_CREDENTIAL::Terminate(void)

- ea: `0x180005fc8`
- end: `0x180006072`
- name: `?Terminate@SSPI_CREDENTIAL@@SAXXZ`
- size: `170`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800042d0`
- `0x180004650`

## callees

- `0x180001064`
- `0x180005fc8`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x18000603b`
- `SspiCli!FreeCredentialsHandle` at `0x18000603b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006052`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006052`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180006048`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180006048`

## pseudocode

```c
void SSPI_CREDENTIAL::Terminate(void)
{
  volatile signed __int32 *v0; // rbx
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY **v2; // rcx

  while ( SSPI_CREDENTIAL::sm_CredentialListHead.Flink != &SSPI_CREDENTIAL::sm_CredentialListHead )
  {
    v0 = (volatile signed __int32 *)&SSPI_CREDENTIAL::sm_CredentialListHead.Flink[-8];
    Flink = SSPI_CREDENTIAL::sm_CredentialListHead.Flink->Flink;
    if ( SSPI_CREDENTIAL::sm_CredentialListHead.Flink->Flink->Blink != SSPI_CREDENTIAL::sm_CredentialListHead.Flink
      || (v2 = (struct _LIST_ENTRY **)*((_QWORD *)v0 + 17), *v2 != SSPI_CREDENTIAL::sm_CredentialListHead.Flink) )
    {
      __fastfail(3u);
    }
    *v2 = Flink;
    Flink->Blink = (struct _LIST_ENTRY *)v2;
    if ( _InterlockedExchangeAdd(v0 + 1, 0xFFFFFFFF) == 1 && v0 )
    {
      *v0 = 1396917094;
      if ( *((_QWORD *)v0 + 25) != -1 && *((_QWORD *)v0 + 26) != -1 )
        FreeCredentialsHandle((PCredHandle)(v0 + 50));
      MULTISZ::~MULTISZ((MULTISZ *)(v0 + 36));
      STRA::~STRA((STRA *)(v0 + 2));
      operator delete((void *)v0);
    }
  }
}

```

## disassembly

```asm
0x180005fc8  push    rbx
0x180005fca  sub     rsp, 20h
0x180005fce  mov     rbx, cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005fd5  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005fdc  cmp     rbx, rax
0x180005fdf  jz      loc_18000606C
0x180005fe5  add     rbx, 0FFFFFFFFFFFFFF80h
0x180005fe9  lea     rax, [rbx+80h]
0x180005ff0  mov     rdx, [rax]
0x180005ff3  cmp     [rdx+8], rax
0x180005ff7  jnz     short loc_180006065
0x180005ff9  mov     rcx, [rbx+88h]
0x180006000  cmp     [rcx], rax
0x180006003  jnz     short loc_180006065
0x180006005  mov     [rcx], rdx
0x180006008  or      eax, 0FFFFFFFFh
0x18000600b  mov     [rdx+8], rcx
0x18000600f  lock xadd [rbx+4], eax
0x180006014  cmp     eax, 1
0x180006017  jnz     short loc_180005FCE
0x180006019  test    rbx, rbx
0x18000601c  jz      short loc_180005FCE
0x18000601e  lea     rcx, [rbx+0C8h]; phCredential
0x180006025  mov     dword ptr [rbx], 53434366h
0x18000602b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000602f  jz      short loc_180006041
0x180006031  cmp     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x180006039  jz      short loc_180006041
0x18000603b  call    cs:__imp_FreeCredentialsHandle
0x180006041  lea     rcx, [rbx+90h]
0x180006048  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000604e  lea     rcx, [rbx+8]
0x180006052  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006058  mov     rcx, rbx; Block
0x18000605b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006060  jmp     loc_180005FCE
0x180006065  mov     ecx, 3
0x18000606a  int     29h; Win8: RtlFailFast(ecx)
0x18000606c  add     rsp, 20h
0x180006070  pop     rbx
0x180006071  retn
```
