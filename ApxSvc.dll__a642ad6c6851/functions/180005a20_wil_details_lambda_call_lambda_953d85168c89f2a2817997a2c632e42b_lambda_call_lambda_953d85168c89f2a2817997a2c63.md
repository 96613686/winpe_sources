# wil::details::lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___::_lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___

- ea: `0x180005a20`
- end: `0x180005ab7`
- name: `wil::details::lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___::_lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___`
- size: `151`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bc4`
- `0x1800080b7`

## callees

- `0x180005a20`
- `0x180006140`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a4e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a60`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___::_lambda_call__lambda_953d85168c89f2a2817997a2c632e42b___(
        __int64 a1)
{
  _BYTE *v1; // rax
  _UNKNOWN **result; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = *(_BYTE **)a1;
    *(_BYTE *)(a1 + 8) = 0;
    if ( *v1 && pti )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(pti, 1);
      CloseThreadpoolTimer(pti);
      pti = 0;
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      return (_UNKNOWN **)WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            12,
                            &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005a20  sub     rsp, 28h
0x180005a24  cmp     byte ptr [rcx+8], 0
0x180005a28  jz      loc_180005AB2
0x180005a2e  mov     rax, [rcx]
0x180005a31  mov     byte ptr [rcx+8], 0
0x180005a35  cmp     byte ptr [rax], 0
0x180005a38  jz      short loc_180005A7E
0x180005a3a  mov     rcx, cs:pti; pti
0x180005a41  test    rcx, rcx
0x180005a44  jz      short loc_180005A7E
0x180005a46  xor     r9d, r9d; msWindowLength
0x180005a49  xor     r8d, r8d; msPeriod
0x180005a4c  xor     edx, edx; pftDueTime
0x180005a4e  call    cs:__imp_SetThreadpoolTimer
0x180005a54  mov     rcx, cs:pti; pti
0x180005a5b  mov     edx, 1; fCancelPendingCallbacks
0x180005a60  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a66  mov     rcx, cs:pti; pti
0x180005a6d  call    cs:__imp_CloseThreadpoolTimer
0x180005a73  mov     cs:pti, 0
0x180005a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a85  lea     rax, WPP_GLOBAL_Control
0x180005a8c  cmp     rcx, rax
0x180005a8f  jz      short loc_180005AB2
0x180005a91  test    byte ptr [rcx+1Ch], 1
0x180005a95  jz      short loc_180005AB2
0x180005a97  cmp     byte ptr [rcx+19h], 5
0x180005a9b  jb      short loc_180005AB2
0x180005a9d  mov     rcx, [rcx+10h]
0x180005aa1  lea     r8, WPP_27ea2efe8112346a6f92681e48c92895_Traceguids
0x180005aa8  mov     edx, 0Ch
0x180005aad  call    WPP_SF_
0x180005ab2  add     rsp, 28h
0x180005ab6  retn
```
