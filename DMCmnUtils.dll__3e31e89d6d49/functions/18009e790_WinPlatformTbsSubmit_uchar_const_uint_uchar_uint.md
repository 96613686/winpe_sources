# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x18009e790`
- end: `0x18009e80a`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `122`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009e790`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x18009e7c4`
- `tbs!Tbsi_Context_Create` at `0x18009e7c4`
- `tbs!Tbsip_Submit_Command` at `0x18009e7f4`
- `tbs!Tbsip_Submit_Command` at `0x18009e7f4`

## pseudocode

```c
int __fastcall WinPlatformTbsSubmit(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)
{
  PVOID v5; // rcx
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
0x18009e790  push    rbx
0x18009e792  push    rbp
0x18009e793  push    rsi
0x18009e794  push    rdi
0x18009e795  sub     rsp, 58h
0x18009e799  mov     rbp, rcx
0x18009e79c  mov     [rsp+78h+pContextParams.version], 1
0x18009e7a4  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18009e7ab  mov     rbx, r9
0x18009e7ae  mov     rdi, r8
0x18009e7b1  mov     esi, edx
0x18009e7b3  test    rcx, rcx
0x18009e7b6  jnz     short loc_18009E7DB
0x18009e7b8  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x18009e7bf  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x18009e7c4  call    cs:__imp_Tbsi_Context_Create
0x18009e7cb  nop     dword ptr [rax+rax+00h]
0x18009e7d0  test    eax, eax
0x18009e7d2  js      short loc_18009E800
0x18009e7d4  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x18009e7db  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x18009e7e0  mov     r9, rbp; pabCommand
0x18009e7e3  mov     [rsp+78h+pabResult], rdi; pabResult
0x18009e7e8  xor     edx, edx; Locality
0x18009e7ea  mov     r8d, 0C8h; Priority
0x18009e7f0  mov     [rsp+78h+cbCommand], esi; cbCommand
0x18009e7f4  call    cs:__imp_Tbsip_Submit_Command
0x18009e7fb  nop     dword ptr [rax+rax+00h]
0x18009e800  add     rsp, 58h
0x18009e804  pop     rdi
0x18009e805  pop     rsi
0x18009e806  pop     rbp
0x18009e807  pop     rbx
0x18009e808  retn
```
