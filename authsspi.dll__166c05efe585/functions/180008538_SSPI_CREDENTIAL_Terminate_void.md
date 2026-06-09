# SSPI_CREDENTIAL::Terminate(void)

- ea: `0x180008538`
- end: `0x1800085e2`
- name: `?Terminate@SSPI_CREDENTIAL@@SAXXZ`
- size: `170`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005be0`
- `0x180006120`

## callees

- `0x180001064`
- `0x180008538`

## import_xrefs

- `SspiCli!FreeCredentialsHandle` at `0x1800085ab`
- `SspiCli!FreeCredentialsHandle` at `0x1800085ab`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085c2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085c2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800085b8`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800085b8`

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
0x180008538  push    rbx
0x18000853a  sub     rsp, 20h
0x18000853e  mov     rbx, cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180008545  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x18000854c  cmp     rbx, rax
0x18000854f  jz      loc_1800085DC
0x180008555  add     rbx, 0FFFFFFFFFFFFFF80h
0x180008559  lea     rax, [rbx+80h]
0x180008560  mov     rdx, [rax]
0x180008563  cmp     [rdx+8], rax
0x180008567  jnz     short loc_1800085D5
0x180008569  mov     rcx, [rbx+88h]
0x180008570  cmp     [rcx], rax
0x180008573  jnz     short loc_1800085D5
0x180008575  mov     [rcx], rdx
0x180008578  or      eax, 0FFFFFFFFh
0x18000857b  mov     [rdx+8], rcx
0x18000857f  lock xadd [rbx+4], eax
0x180008584  cmp     eax, 1
0x180008587  jnz     short loc_18000853E
0x180008589  test    rbx, rbx
0x18000858c  jz      short loc_18000853E
0x18000858e  lea     rcx, [rbx+0C8h]; phCredential
0x180008595  mov     dword ptr [rbx], 53434366h
0x18000859b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000859f  jz      short loc_1800085B1
0x1800085a1  cmp     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x1800085a9  jz      short loc_1800085B1
0x1800085ab  call    cs:__imp_FreeCredentialsHandle
0x1800085b1  lea     rcx, [rbx+90h]
0x1800085b8  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800085be  lea     rcx, [rbx+8]
0x1800085c2  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800085c8  mov     rcx, rbx; Block
0x1800085cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800085d0  jmp     loc_18000853E
0x1800085d5  mov     ecx, 3
0x1800085da  int     29h; Win8: RtlFailFast(ecx)
0x1800085dc  add     rsp, 20h
0x1800085e0  pop     rbx
0x1800085e1  retn
```
