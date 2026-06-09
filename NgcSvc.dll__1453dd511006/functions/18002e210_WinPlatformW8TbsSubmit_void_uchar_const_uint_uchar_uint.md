# WinPlatformW8TbsSubmit(void *,uchar * const,uint,uchar *,uint *)

- ea: `0x18002e210`
- end: `0x18002e2b9`
- name: `?WinPlatformW8TbsSubmit@@YAIPEAXQEAEIPEAEPEAI@Z`
- size: `169`
- prototype: `unsigned int(void *, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002e210`

## import_xrefs

- `tbs!Tbsip_Submit_Command` at `0x18002e256`
- `tbs!Tbsip_Submit_Command` at `0x18002e256`
- `tbs!Tbsi_Context_Create` at `0x18002e288`
- `tbs!Tbsi_Context_Create` at `0x18002e288`
- `tbs!Tbsip_Context_Close` at `0x18002e2a7`
- `tbs!Tbsip_Context_Close` at `0x18002e2a7`

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
    goto LABEL_3;
  }
  v8 = g_hTbs;
  if ( g_hTbs )
    goto LABEL_3;
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
LABEL_3:
    phContext = v8;
    return Tbsip_Submit_Command(v8, 0, 0xC8u, a2, a3, a4, pcbResult);
  }
  return result;
}

```

## disassembly

```asm
0x18002e210  push    rbp
0x18002e212  push    rbx
0x18002e213  push    rsi
0x18002e214  push    rdi
0x18002e215  mov     rbp, rsp
0x18002e218  sub     rsp, 58h
0x18002e21c  mov     [rbp+phContext], 0
0x18002e224  mov     rbx, r9
0x18002e227  mov     edi, r8d
0x18002e22a  mov     rsi, rdx
0x18002e22d  test    rcx, rcx
0x18002e230  jz      short loc_18002E265
0x18002e232  mov     rcx, [rcx]; hContext
0x18002e235  mov     [rbp+phContext], rcx
0x18002e239  mov     rax, [rbp+arg_20]
0x18002e23d  mov     r9, rsi; pabCommand
0x18002e240  mov     [rsp+58h+pcbResult], rax; pcbResult
0x18002e245  xor     edx, edx; Locality
0x18002e247  mov     [rsp+58h+pabResult], rbx; pabResult
0x18002e24c  mov     r8d, 0C8h; Priority
0x18002e252  mov     [rsp+58h+cbCommand], edi; cbCommand
0x18002e256  call    cs:__imp_Tbsip_Submit_Command
0x18002e25c  add     rsp, 58h
0x18002e260  pop     rdi
0x18002e261  pop     rsi
0x18002e262  pop     rbx
0x18002e263  pop     rbp
0x18002e264  retn
0x18002e265  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18002e26c  test    rcx, rcx
0x18002e26f  jnz     short loc_18002E235
0x18002e271  mov     qword ptr [rbp+pContextParams.version], rcx
0x18002e275  lea     rdx, [rbp+phContext]; phContext
0x18002e279  or      [rbp+pContextParams.version+4], 4
0x18002e27d  lea     rcx, [rbp+pContextParams]; pContextParams
0x18002e281  mov     [rbp+pContextParams.version], 2
0x18002e288  call    cs:__imp_Tbsi_Context_Create
0x18002e28e  test    eax, eax
0x18002e290  js      short loc_18002E25C
0x18002e292  mov     rcx, [rbp+phContext]
0x18002e296  xor     eax, eax
0x18002e298  lock cmpxchg cs:?g_hTbs@@3PEAXEA, rcx; void * g_hTbs
0x18002e2a1  mov     rcx, [rbp+phContext]; hContext
0x18002e2a5  jz      short loc_18002E239
0x18002e2a7  call    cs:__imp_Tbsip_Context_Close
0x18002e2ad  mov     rcx, cs:?g_hTbs@@3PEAXEA; void * g_hTbs
0x18002e2b4  jmp     loc_18002E235
```
