# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x18009e810`
- end: `0x18009e8c9`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `185`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009e810`

## import_xrefs

- `tbs!Tbsi_Context_Create` at `0x18009e85a`
- `tbs!Tbsi_Context_Create` at `0x18009e85a`
- `tbs!Tbsip_Submit_Command` at `0x18009e8b3`
- `tbs!Tbsip_Submit_Command` at `0x18009e8b3`
- `tbs!Tbsip_Context_Close` at `0x18009e87f`
- `tbs!Tbsip_Context_Close` at `0x18009e87f`

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
0x18009e810  push    rbp
0x18009e812  push    rbx
0x18009e813  push    rsi
0x18009e814  push    rdi
0x18009e815  mov     rbp, rsp
0x18009e818  sub     rsp, 58h
0x18009e81c  mov     [rbp+phContext], 0
0x18009e824  mov     rbx, r9
0x18009e827  mov     edi, r8d
0x18009e82a  mov     rsi, rdx
0x18009e82d  test    rcx, rcx
0x18009e830  jz      short loc_18009E837
0x18009e832  mov     rcx, [rcx]
0x18009e835  jmp     short loc_18009E892
0x18009e837  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18009e83e  test    rcx, rcx
0x18009e841  jnz     short loc_18009E892
0x18009e843  mov     qword ptr [rbp+pContextParams.version], rcx
0x18009e847  lea     rdx, [rbp+phContext]; phContext
0x18009e84b  or      [rbp+pContextParams.version+4], 4
0x18009e84f  lea     rcx, [rbp+pContextParams]; pContextParams
0x18009e853  mov     [rbp+pContextParams.version], 2
0x18009e85a  call    cs:__imp_Tbsi_Context_Create
0x18009e861  nop     dword ptr [rax+rax+00h]
0x18009e866  test    eax, eax
0x18009e868  js      short loc_18009E8BF
0x18009e86a  mov     rcx, [rbp+phContext]
0x18009e86e  xor     eax, eax
0x18009e870  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x18009e879  mov     rcx, [rbp+phContext]; hContext
0x18009e87d  jz      short loc_18009E896
0x18009e87f  call    cs:__imp_Tbsip_Context_Close
0x18009e886  nop     dword ptr [rax+rax+00h]
0x18009e88b  mov     rcx, cs:?g_hTbs@@3PEAXEA; hContext
0x18009e892  mov     [rbp+phContext], rcx
0x18009e896  mov     rax, [rbp+arg_20]
0x18009e89a  mov     r9, rsi; pabCommand
0x18009e89d  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18009e8a2  xor     edx, edx; Locality
0x18009e8a4  mov     [rsp+58h+pabResult], rbx; pabResult
0x18009e8a9  mov     r8d, 0C8h; Priority
0x18009e8af  mov     [rsp+58h+cbCommand], edi; cbCommand
0x18009e8b3  call    cs:__imp_Tbsip_Submit_Command
0x18009e8ba  nop     dword ptr [rax+rax+00h]
0x18009e8bf  add     rsp, 58h
0x18009e8c3  pop     rdi
0x18009e8c4  pop     rsi
0x18009e8c5  pop     rbx
0x18009e8c6  pop     rbp
0x18009e8c7  retn
```
