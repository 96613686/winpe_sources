# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x1800496d0`
- end: `0x1800497ae`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `222`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800496d0`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x18004972a`
- `tbs!Tbsip_Submit_Command` at `0x18004972a`
- `tbs!Tbsip_Context_Close` at `0x18004978e`
- `tbs!Tbsip_Context_Close` at `0x18004978e`
- `tbs!Tbsi_Context_Create` at `0x180049763`
- `tbs!Tbsi_Context_Create` at `0x180049763`

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
  PVOID phContext; // [rsp+60h] [rbp+8h] BYREF

  phContext = 0;
  if ( a1 )
  {
    v8 = *a1;
    goto LABEL_3;
  }
  v8 = g_hTbs;
  if ( g_hTbs )
  {
LABEL_3:
    phContext = v8;
    return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
  }
  pContextParams[1].version = 4;
  pContextParams[0].version = 2;
  result = Tbsi_Context_Create(pContextParams, &phContext);
  if ( result >= 0 )
  {
    v8 = phContext;
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&g_hTbs, (signed __int64)phContext, 0) )
      return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
    Tbsip_Context_Close(phContext);
    v8 = g_hTbs;
    goto LABEL_3;
  }
  return result;
}

```

## disassembly

```asm
0x1800496d0  mov     [rsp+arg_8], rbx
0x1800496d5  mov     [rsp+arg_10], rsi
0x1800496da  push    rdi
0x1800496db  sub     rsp, 50h
0x1800496df  xor     eax, eax
0x1800496e1  mov     rbx, r9
0x1800496e4  mov     [rsp+58h+phContext], rax
0x1800496e9  mov     edi, r8d
0x1800496ec  mov     rsi, rdx
0x1800496ef  test    rcx, rcx
0x1800496f2  jnz     loc_1800497A6
0x1800496f8  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x1800496ff  test    rcx, rcx
0x180049702  jz      short loc_180049747
0x180049704  mov     [rsp+58h+phContext], rcx
0x180049709  mov     rax, [rsp+58h+arg_20]
0x180049711  mov     r9, rsi; pabCommand
0x180049714  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180049719  xor     edx, edx; Locality
0x18004971b  mov     [rsp+58h+pabResult], rbx; pabResult
0x180049720  mov     r8d, 0C8h; Priority
0x180049726  mov     [rsp+58h+cbCommand], edi; cbCommand
0x18004972a  call    cs:__imp_Tbsip_Submit_Command
0x180049731  nop     dword ptr [rax+rax+00h]
0x180049736  mov     rbx, [rsp+58h+arg_8]
0x18004973b  mov     rsi, [rsp+58h+arg_10]
0x180049740  add     rsp, 50h
0x180049744  pop     rdi
0x180049745  retn
0x180049747  mov     qword ptr [rsp+58h+pContextParams.version], rax
0x18004974c  lea     rdx, [rsp+58h+phContext]; phContext
0x180049751  or      [rsp+58h+pContextParams.version+4], 4
0x180049756  lea     rcx, [rsp+58h+pContextParams]; pContextParams
0x18004975b  mov     [rsp+58h+pContextParams.version], 2
0x180049763  call    cs:__imp_Tbsi_Context_Create
0x18004976a  nop     dword ptr [rax+rax+00h]
0x18004976f  test    eax, eax
0x180049771  js      short loc_180049736
0x180049773  mov     rcx, [rsp+58h+phContext]
0x180049778  xor     eax, eax
0x18004977a  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x180049783  mov     rcx, [rsp+58h+phContext]; hContext
0x180049788  jz      loc_180049709
0x18004978e  call    cs:__imp_Tbsip_Context_Close
0x180049795  nop     dword ptr [rax+rax+00h]
0x18004979a  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x1800497a1  jmp     loc_180049704
0x1800497a6  mov     rcx, [rcx]
0x1800497a9  jmp     loc_180049704
```
