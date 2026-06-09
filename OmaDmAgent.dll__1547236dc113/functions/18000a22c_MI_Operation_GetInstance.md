# MI_Operation_GetInstance

- ea: `0x18000a22c`
- end: `0x18000a287`
- name: `MI_Operation_GetInstance`
- size: `91`
- prototype: `static MI_Result __stdcall(MI_Operation *operation, const MI_Instance **instance, MI_Boolean *moreResults, MI_Result *result, const MI_Char **errorMessage, const MI_Instance **completionDetails)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007edc`
- `0x180009304`

## callees

- `0x18000a22c`
- `0x180021010`

## pseudocode

```c
MI_Result __stdcall MI_Operation_GetInstance(
        MI_Operation *operation,
        const MI_Instance **instance,
        MI_Boolean *moreResults,
        MI_Result *result,
        const MI_Char **errorMessage,
        const MI_Instance **completionDetails)
{
  const MI_OperationFT *ft; // r10

  if ( operation )
  {
    ft = operation->ft;
    if ( ft )
      return ((unsigned int (__fastcall *)(MI_Operation *, const MI_Instance **, MI_Boolean *, MI_Result *, const MI_Char **, const MI_Instance **))ft->GetInstance)(
               operation,
               instance,
               moreResults,
               result,
               errorMessage,
               completionDetails);
  }
  if ( result )
    *result = MI_RESULT_INVALID_PARAMETER;
  if ( moreResults )
    *moreResults = 0;
  return 4;
}

```

## disassembly

```asm
0x18000a22c  sub     rsp, 48h
0x18000a230  mov     rax, r9
0x18000a233  mov     r11, rdx
0x18000a236  test    rcx, rcx
0x18000a239  jz      short loc_18000A269
0x18000a23b  mov     r10, [rcx+10h]
0x18000a23f  test    r10, r10
0x18000a242  jz      short loc_18000A269
0x18000a244  mov     r9, [rsp+48h+completionDetails]
0x18000a249  mov     rdx, [rsp+48h+errorMessage]
0x18000a24e  mov     [rsp+48h+var_20], r9
0x18000a253  mov     r9, rax
0x18000a256  mov     rax, [r10+18h]
0x18000a25a  mov     [rsp+48h+var_28], rdx
0x18000a25f  mov     rdx, r11
0x18000a262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a267  jmp     short loc_18000A281
0x18000a269  mov     ecx, 4
0x18000a26e  test    rax, rax
0x18000a271  jz      short loc_18000A276
0x18000a273  mov     [r9], ecx
0x18000a276  test    r8, r8
0x18000a279  jz      short loc_18000A27F
0x18000a27b  mov     byte ptr [r8], 0
0x18000a27f  mov     eax, ecx
0x18000a281  add     rsp, 48h
0x18000a285  retn
```
