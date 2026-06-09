# RAiLogonWithSmartCardCreds

- ea: `0x18003e220`
- end: `0x18003e34d`
- name: `RAiLogonWithSmartCardCreds`
- size: `301`
- prototype: `_UNKNOWN **__fastcall(PRPC_ASYNC_STATE pAsync, void *, char, WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009d50`
- `0x180026f40`
- `0x1800290b4`
- `0x18003e220`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003e30c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003e30c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e286`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e286`

## pseudocode

```c
_UNKNOWN **__fastcall RAiLogonWithSmartCardCreds(PRPC_ASYNC_STATE pAsync, void *a2, char a3, WCHAR *a4, __int64 a5)
{
  int *v8; // rax
  _UNKNOWN **result; // rax
  DWORD Reply; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-24h] BYREF
  void *v12; // [rsp+58h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h] BYREF
  void *v14; // [rsp+68h] [rbp-10h] BYREF

  v12 = 0;
  v13 = 0;
  v11 = 0;
  Reply = AiGetClientInformation(a2, &v14, &v12, &v11, 0);
  if ( !Reply )
  {
    v8 = (int *)LocalAlloc(0x40u, 0xD0u);
    if ( v8 )
    {
      *v8 = 208;
      v8[1] = 4;
      v8[50] = 1;
      Reply = AiLaunchConsentUI(v12, v8, a4, a5, v11, (a3 & 0x10 | 0x800) << 7, 6u, 0xFFFFFFFF, 0, &v13);
    }
    else
    {
      Reply = 8;
    }
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (_UNKNOWN **)WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          10,
                          WPP_b23fa736e9853481a42645a0499c03f5_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18003e220  push    rbp
0x18003e222  push    rbx
0x18003e223  push    rsi
0x18003e224  push    rdi
0x18003e225  mov     rbp, rsp
0x18003e228  sub     rsp, 78h
0x18003e22c  mov     rax, rdx
0x18003e22f  mov     [rbp+Reply], 0
0x18003e236  mov     rsi, r9
0x18003e239  mov     [rbp+var_20], 0
0x18003e241  mov     ebx, r8d
0x18003e244  mov     [rbp+var_18], 0
0x18003e24c  mov     rdi, rcx
0x18003e24f  mov     [rbp+var_24], 0
0x18003e256  mov     rcx, rax; void *
0x18003e259  mov     [rsp+78h+var_58], 0; unsigned int *
0x18003e262  lea     r9, [rbp+var_24]; unsigned int *
0x18003e266  lea     r8, [rbp+var_20]; void **
0x18003e26a  lea     rdx, [rbp+var_10]; void **
0x18003e26e  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003e273  mov     [rbp+Reply], eax
0x18003e276  test    eax, eax
0x18003e278  jnz     loc_18003E305
0x18003e27e  mov     edx, 0D0h; uBytes
0x18003e283  lea     ecx, [rax+40h]; uFlags
0x18003e286  call    cs:__imp_LocalAlloc
0x18003e28c  mov     rdx, rax
0x18003e28f  test    rax, rax
0x18003e292  jnz     short loc_18003E29D
0x18003e294  mov     [rbp+Reply], 8
0x18003e29b  jmp     short loc_18003E305
0x18003e29d  mov     dword ptr [rax], 0D0h
0x18003e2a3  mov     dword ptr [rax+4], 4
0x18003e2aa  mov     dword ptr [rax+0C8h], 1
0x18003e2b4  mov     r9, [rbp+arg_20]
0x18003e2b8  lea     rax, [rbp+var_18]
0x18003e2bc  mov     rcx, [rbp+var_20]
0x18003e2c0  and     ebx, 10h
0x18003e2c3  mov     [rsp+78h+var_30], rax
0x18003e2c8  bts     ebx, 0Bh
0x18003e2cc  mov     eax, [rbp+var_24]
0x18003e2cf  mov     r8, rsi
0x18003e2d2  mov     [rsp+78h+var_38], 0
0x18003e2db  mov     [rsp+78h+var_40], 0FFFFFFFFh
0x18003e2e3  shl     ebx, 7
0x18003e2e6  mov     [rsp+78h+var_48], 6
0x18003e2ee  mov     [rsp+78h+var_50], ebx
0x18003e2f2  mov     dword ptr [rsp+78h+var_58], eax
0x18003e2f6  mov     [rbp+Reply], 0
0x18003e2fd  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18003e302  mov     [rbp+Reply], eax
0x18003e305  lea     rdx, [rbp+Reply]; Reply
0x18003e309  mov     rcx, rdi; pAsync
0x18003e30c  call    cs:__imp_RpcAsyncCompleteCall
0x18003e312  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e319  lea     rax, WPP_GLOBAL_Control
0x18003e320  cmp     rcx, rax
0x18003e323  jz      short loc_18003E344
0x18003e325  test    byte ptr [rcx+1Ch], 1
0x18003e329  jz      short loc_18003E344
0x18003e32b  mov     r9d, [rbp+Reply]
0x18003e32f  lea     r8, WPP_b23fa736e9853481a42645a0499c03f5_Traceguids
0x18003e336  mov     rcx, [rcx+10h]
0x18003e33a  mov     edx, 0Ah
0x18003e33f  call    WPP_SF_D
0x18003e344  add     rsp, 78h
0x18003e348  pop     rdi
0x18003e349  pop     rsi
0x18003e34a  pop     rbx
0x18003e34b  pop     rbp
0x18003e34c  retn
```
