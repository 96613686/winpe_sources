# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x180040590`
- end: `0x1800405fd`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `109`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180040590`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x1800405c4`
- `tbs!Tbsi_Context_Create` at `0x1800405c4`
- `tbs!Tbsip_Submit_Command` at `0x1800405ee`
- `tbs!Tbsip_Submit_Command` at `0x1800405ee`

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
0x180040590  push    rbx
0x180040592  push    rbp
0x180040593  push    rsi
0x180040594  push    rdi
0x180040595  sub     rsp, 58h
0x180040599  mov     rbp, rcx
0x18004059c  mov     [rsp+78h+pContextParams.version], 1
0x1800405a4  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x1800405ab  mov     rbx, r9
0x1800405ae  mov     rdi, r8
0x1800405b1  mov     esi, edx
0x1800405b3  test    rcx, rcx
0x1800405b6  jnz     short loc_1800405D5
0x1800405b8  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x1800405bf  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x1800405c4  call    cs:__imp_Tbsi_Context_Create
0x1800405ca  test    eax, eax
0x1800405cc  js      short loc_1800405F4
0x1800405ce  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x1800405d5  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x1800405da  mov     r9, rbp; pabCommand
0x1800405dd  mov     [rsp+78h+pabResult], rdi; pabResult
0x1800405e2  xor     edx, edx; Locality
0x1800405e4  mov     r8d, 0C8h; Priority
0x1800405ea  mov     [rsp+78h+cbCommand], esi; cbCommand
0x1800405ee  call    cs:__imp_Tbsip_Submit_Command
0x1800405f4  add     rsp, 58h
0x1800405f8  pop     rdi
0x1800405f9  pop     rsi
0x1800405fa  pop     rbp
0x1800405fb  pop     rbx
0x1800405fc  retn
```
