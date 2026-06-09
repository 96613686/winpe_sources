# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x180058b80`
- end: `0x180058bfa`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `122`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180058b80`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x180058be4`
- `tbs!Tbsip_Submit_Command` at `0x180058be4`
- `tbs!Tbsi_Context_Create` at `0x180058bb4`
- `tbs!Tbsi_Context_Create` at `0x180058bb4`

## pseudocode

```c
int __fastcall WinPlatformTbsSubmit(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)
{
  TBS_HCONTEXT v5; // rcx
  int result; // eax
  TBS_CONTEXT_PARAMS pContextParams; // [rsp+40h] [rbp-38h] BYREF

  pContextParams.version = 1;
  v5 = g_hTbs;
  if ( !g_hTbs )
  {
    result = Tbsi_Context_Create(&pContextParams, &g_hTbs);
    if ( result < 0 )
      return result;
    v5 = g_hTbs;
  }
  return Tbsip_Submit_Command(v5, 0, 0xC8u, pabCommand, cbCommand, pabResult, pcbResult);
}

```

## disassembly

```asm
0x180058b80  push    rbx
0x180058b82  push    rbp
0x180058b83  push    rsi
0x180058b84  push    rdi
0x180058b85  sub     rsp, 58h
0x180058b89  mov     rbp, rcx
0x180058b8c  mov     [rsp+78h+pContextParams.version], 1
0x180058b94  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x180058b9b  mov     rbx, r9
0x180058b9e  mov     rdi, r8
0x180058ba1  mov     esi, edx
0x180058ba3  test    rcx, rcx
0x180058ba6  jnz     short loc_180058BCB
0x180058ba8  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x180058baf  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x180058bb4  call    cs:__imp_Tbsi_Context_Create
0x180058bbb  nop     dword ptr [rax+rax+00h]
0x180058bc0  test    eax, eax
0x180058bc2  js      short loc_180058BF0
0x180058bc4  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x180058bcb  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x180058bd0  mov     r9, rbp; pabCommand
0x180058bd3  mov     [rsp+78h+pabResult], rdi; pabResult
0x180058bd8  xor     edx, edx; Locality
0x180058bda  mov     r8d, 0C8h; Priority
0x180058be0  mov     [rsp+78h+cbCommand], esi; cbCommand
0x180058be4  call    cs:__imp_Tbsip_Submit_Command
0x180058beb  nop     dword ptr [rax+rax+00h]
0x180058bf0  add     rsp, 58h
0x180058bf4  pop     rdi
0x180058bf5  pop     rsi
0x180058bf6  pop     rbp
0x180058bf7  pop     rbx
0x180058bf8  retn
```
