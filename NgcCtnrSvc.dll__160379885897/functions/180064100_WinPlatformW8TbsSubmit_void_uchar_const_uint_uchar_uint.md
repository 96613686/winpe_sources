# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x180064100`
- end: `0x1800641b9`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `185`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180064100`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x1800641a3`
- `tbs!Tbsip_Submit_Command` at `0x1800641a3`
- `tbs!Tbsi_Context_Create` at `0x18006414a`
- `tbs!Tbsi_Context_Create` at `0x18006414a`
- `tbs!Tbsip_Context_Close` at `0x18006416f`
- `tbs!Tbsip_Context_Close` at `0x18006416f`

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
0x180064100  push    rbp
0x180064102  push    rbx
0x180064103  push    rsi
0x180064104  push    rdi
0x180064105  mov     rbp, rsp
0x180064108  sub     rsp, 58h
0x18006410c  mov     [rbp+phContext], 0
0x180064114  mov     rbx, r9
0x180064117  mov     edi, r8d
0x18006411a  mov     rsi, rdx
0x18006411d  test    rcx, rcx
0x180064120  jz      short loc_180064127
0x180064122  mov     rcx, [rcx]
0x180064125  jmp     short loc_180064182
0x180064127  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18006412e  test    rcx, rcx
0x180064131  jnz     short loc_180064182
0x180064133  mov     qword ptr [rbp+pContextParams.version], rcx
0x180064137  lea     rdx, [rbp+phContext]; phContext
0x18006413b  or      [rbp+pContextParams.version+4], 4
0x18006413f  lea     rcx, [rbp+pContextParams]; pContextParams
0x180064143  mov     [rbp+pContextParams.version], 2
0x18006414a  call    cs:__imp_Tbsi_Context_Create
0x180064151  nop     dword ptr [rax+rax+00h]
0x180064156  test    eax, eax
0x180064158  js      short loc_1800641AF
0x18006415a  mov     rcx, [rbp+phContext]
0x18006415e  xor     eax, eax
0x180064160  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x180064169  mov     rcx, [rbp+phContext]; hContext
0x18006416d  jz      short loc_180064186
0x18006416f  call    cs:__imp_Tbsip_Context_Close
0x180064176  nop     dword ptr [rax+rax+00h]
0x18006417b  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x180064182  mov     [rbp+phContext], rcx
0x180064186  mov     rax, [rbp+arg_20]
0x18006418a  mov     r9, rsi; pabCommand
0x18006418d  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180064192  xor     edx, edx; Locality
0x180064194  mov     [rsp+58h+pabResult], rbx; pabResult
0x180064199  mov     r8d, 0C8h; Priority
0x18006419f  mov     [rsp+58h+cbCommand], edi; cbCommand
0x1800641a3  call    cs:__imp_Tbsip_Submit_Command
0x1800641aa  nop     dword ptr [rax+rax+00h]
0x1800641af  add     rsp, 58h
0x1800641b3  pop     rdi
0x1800641b4  pop     rsi
0x1800641b5  pop     rbx
0x1800641b6  pop     rbp
0x1800641b7  retn
```
