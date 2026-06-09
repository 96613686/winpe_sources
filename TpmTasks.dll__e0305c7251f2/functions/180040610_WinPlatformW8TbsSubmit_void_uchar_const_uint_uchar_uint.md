# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x180040610`
- end: `0x1800406b6`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `166`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180040610`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x18004065a`
- `tbs!Tbsi_Context_Create` at `0x18004065a`
- `tbs!Tbsip_Submit_Command` at `0x1800406a7`
- `tbs!Tbsip_Submit_Command` at `0x1800406a7`
- `tbs!Tbsip_Context_Close` at `0x180040679`
- `tbs!Tbsip_Context_Close` at `0x180040679`

## pseudocode

```c
int __fastcall WinPlatformW8TbsSubmit(
        PVOID *a1,
        unsigned __int8 *const a2,
        UINT32 a3,
        unsigned __int8 *a4,
        unsigned int *pcbResult)
{
  PVOID v8; // rcx
  int result; // eax
  TBS_CONTEXT_PARAMS pContextParams[2]; // [rsp+40h] [rbp-18h] BYREF
  PVOID phContext; // [rsp+80h] [rbp+28h] BYREF

  phContext = 0;
  if ( a1 )
  {
    v8 = *a1;
LABEL_7:
    phContext = v8;
    return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
  }
  v8 = g_hTbs;
  if ( g_hTbs )
    goto LABEL_7;
  pContextParams[1].version = 4;
  pContextParams[0].version = 2;
  result = Tbsi_Context_Create(pContextParams, &phContext);
  if ( result < 0 )
    return result;
  v8 = phContext;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hTbs, (signed __int64)phContext, 0) )
  {
    Tbsip_Context_Close(phContext);
    v8 = g_hTbs;
    goto LABEL_7;
  }
  return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
}

```

## disassembly

```asm
0x180040610  push    rbp
0x180040612  push    rbx
0x180040613  push    rsi
0x180040614  push    rdi
0x180040615  mov     rbp, rsp
0x180040618  sub     rsp, 58h
0x18004061c  mov     [rbp+phContext], 0
0x180040624  mov     rbx, r9
0x180040627  mov     edi, r8d
0x18004062a  mov     rsi, rdx
0x18004062d  test    rcx, rcx
0x180040630  jz      short loc_180040637
0x180040632  mov     rcx, [rcx]
0x180040635  jmp     short loc_180040686
0x180040637  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18004063e  test    rcx, rcx
0x180040641  jnz     short loc_180040686
0x180040643  mov     qword ptr [rbp+pContextParams.version], rcx
0x180040647  lea     rdx, [rbp+phContext]; phContext
0x18004064b  or      [rbp+pContextParams.version+4], 4
0x18004064f  lea     rcx, [rbp+pContextParams]; pContextParams
0x180040653  mov     [rbp+pContextParams.version], 2
0x18004065a  call    cs:__imp_Tbsi_Context_Create
0x180040660  test    eax, eax
0x180040662  js      short loc_1800406AD
0x180040664  mov     rcx, [rbp+phContext]
0x180040668  xor     eax, eax
0x18004066a  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x180040673  mov     rcx, [rbp+phContext]; hContext
0x180040677  jz      short loc_18004068A
0x180040679  call    cs:__imp_Tbsip_Context_Close
0x18004067f  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x180040686  mov     [rbp+phContext], rcx
0x18004068a  mov     rax, [rbp+arg_20]
0x18004068e  mov     r9, rsi; pabCommand
0x180040691  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180040696  xor     edx, edx; Locality
0x180040698  mov     [rsp+58h+pabResult], rbx; pabResult
0x18004069d  mov     r8d, 0C8h; Priority
0x1800406a3  mov     [rsp+58h+cbCommand], edi; cbCommand
0x1800406a7  call    cs:__imp_Tbsip_Submit_Command
0x1800406ad  add     rsp, 58h
0x1800406b1  pop     rdi
0x1800406b2  pop     rsi
0x1800406b3  pop     rbx
0x1800406b4  pop     rbp
0x1800406b5  retn
```
