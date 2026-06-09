# WinPlatformTbsSubmit(uchar * const,uint,uchar *,uint *)

- ea: `0x180064080`
- end: `0x1800640fa`
- name: `?WinPlatformTbsSubmit@@YAIQEAEIPEAEPEAI@Z`
- size: `122`
- prototype: `unsigned int __fastcall(PCBYTE pabCommand, UINT32 cbCommand, PBYTE pabResult, PUINT32 pcbResult)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180064080`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x1800640e4`
- `tbs!Tbsip_Submit_Command` at `0x1800640e4`
- `tbs!Tbsi_Context_Create` at `0x1800640b4`
- `tbs!Tbsi_Context_Create` at `0x1800640b4`

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
0x180064080  push    rbx
0x180064082  push    rbp
0x180064083  push    rsi
0x180064084  push    rdi
0x180064085  sub     rsp, 58h
0x180064089  mov     rbp, rcx
0x18006408c  mov     [rsp+78h+pContextParams.version], 1
0x180064094  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18006409b  mov     rbx, r9
0x18006409e  mov     rdi, r8
0x1800640a1  mov     esi, edx
0x1800640a3  test    rcx, rcx
0x1800640a6  jnz     short loc_1800640CB
0x1800640a8  lea     rdx, ?g_hTbs@@3PEAXEA; phContext
0x1800640af  lea     rcx, [rsp+78h+pContextParams]; pContextParams
0x1800640b4  call    cs:__imp_Tbsi_Context_Create
0x1800640bb  nop     dword ptr [rax+rax+00h]
0x1800640c0  test    eax, eax
0x1800640c2  js      short loc_1800640F0
0x1800640c4  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x1800640cb  mov     [rsp+78h+pcbResult], rbx; pcbResult
0x1800640d0  mov     r9, rbp; pabCommand
0x1800640d3  mov     [rsp+78h+pabResult], rdi; pabResult
0x1800640d8  xor     edx, edx; Locality
0x1800640da  mov     r8d, 0C8h; Priority
0x1800640e0  mov     [rsp+78h+cbCommand], esi; cbCommand
0x1800640e4  call    cs:__imp_Tbsip_Submit_Command
0x1800640eb  nop     dword ptr [rax+rax+00h]
0x1800640f0  add     rsp, 58h
0x1800640f4  pop     rdi
0x1800640f5  pop     rsi
0x1800640f6  pop     rbp
0x1800640f7  pop     rbx
0x1800640f8  retn
```
