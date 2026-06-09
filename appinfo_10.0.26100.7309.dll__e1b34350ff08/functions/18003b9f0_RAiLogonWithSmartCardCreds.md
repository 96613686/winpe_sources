# RAiLogonWithSmartCardCreds

- ea: `0x18003b9f0`
- end: `0x18003bb21`
- name: `RAiLogonWithSmartCardCreds`
- size: `305`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a230`
- `0x1800234a0`
- `0x180024a98`
- `0x18003b9f0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bacc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bacc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ba4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ba4d`

## pseudocode

```c
_UNKNOWN **__fastcall RAiLogonWithSmartCardCreds(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        char a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  int *v8; // rax
  _UNKNOWN **result; // rax
  unsigned int Reply; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-1Ch] BYREF
  void *v12; // [rsp+58h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h] BYREF
  void *v14; // [rsp+68h] [rbp-8h] BYREF

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
                          &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18003b9f0  mov     r11, rsp
0x18003b9f3  mov     [r11+8], rbx
0x18003b9f7  mov     [r11+10h], rsi
0x18003b9fb  mov     [r11+18h], rdi
0x18003b9ff  push    rbp
0x18003ba00  mov     rbp, rsp
0x18003ba03  sub     rsp, 70h
0x18003ba07  and     [rbp+var_18], 0
0x18003ba0c  mov     rax, rdx
0x18003ba0f  and     [rbp+var_10], 0
0x18003ba14  lea     rdx, [rbp+var_8]; void **
0x18003ba18  and     [rbp+var_1C], 0
0x18003ba1c  mov     rsi, r9
0x18003ba1f  and     qword ptr [r11-58h], 0
0x18003ba24  lea     r9, [rbp+var_1C]; unsigned int *
0x18003ba28  mov     ebx, r8d
0x18003ba2b  mov     rdi, rcx
0x18003ba2e  mov     rcx, rax; void *
0x18003ba31  lea     r8, [rbp+var_18]; void **
0x18003ba35  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003ba3a  mov     [rbp+Reply], eax
0x18003ba3d  test    eax, eax
0x18003ba3f  jnz     loc_18003BAC5
0x18003ba45  mov     edx, 0D0h; uBytes
0x18003ba4a  lea     ecx, [rax+40h]; uFlags
0x18003ba4d  call    cs:__imp_LocalAlloc
0x18003ba54  nop     dword ptr [rax+rax+00h]
0x18003ba59  mov     rdx, rax
0x18003ba5c  test    rax, rax
0x18003ba5f  jnz     short loc_18003BA6A
0x18003ba61  mov     [rbp+Reply], 8
0x18003ba68  jmp     short loc_18003BAC5
0x18003ba6a  mov     dword ptr [rax], 0D0h
0x18003ba70  mov     dword ptr [rax+4], 4
0x18003ba77  mov     dword ptr [rax+0C8h], 1
0x18003ba81  mov     r9, [rbp+arg_20]
0x18003ba85  lea     rax, [rbp+var_10]
0x18003ba89  mov     rcx, [rbp+var_18]
0x18003ba8d  and     ebx, 10h
0x18003ba90  mov     [rsp+70h+var_28], rax
0x18003ba95  bts     ebx, 0Bh
0x18003ba99  and     [rsp+70h+var_30], 0
0x18003ba9f  mov     r8, rsi
0x18003baa2  or      [rsp+70h+var_38], 0FFFFFFFFh
0x18003baa7  mov     eax, [rbp+var_1C]
0x18003baaa  shl     ebx, 7
0x18003baad  mov     [rsp+70h+var_40], 6
0x18003bab5  mov     [rsp+70h+var_48], ebx
0x18003bab9  mov     [rsp+70h+var_50], eax
0x18003babd  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18003bac2  mov     [rbp+Reply], eax
0x18003bac5  lea     rdx, [rbp+Reply]; Reply
0x18003bac9  mov     rcx, rdi; pAsync
0x18003bacc  call    cs:__imp_RpcAsyncCompleteCall
0x18003bad3  nop     dword ptr [rax+rax+00h]
0x18003bad8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003badf  lea     rax, WPP_GLOBAL_Control
0x18003bae6  cmp     rcx, rax
0x18003bae9  jz      short loc_18003BB0A
0x18003baeb  test    byte ptr [rcx+1Ch], 1
0x18003baef  jz      short loc_18003BB0A
0x18003baf1  mov     r9d, [rbp+Reply]
0x18003baf5  lea     r8, WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids
0x18003bafc  mov     rcx, [rcx+10h]
0x18003bb00  mov     edx, 0Ah
0x18003bb05  call    WPP_SF_D
0x18003bb0a  lea     r11, [rsp+70h+var_s0]
0x18003bb0f  mov     rbx, [r11+10h]
0x18003bb13  mov     rsi, [r11+18h]
0x18003bb17  mov     rdi, [r11+20h]
0x18003bb1b  mov     rsp, r11
0x18003bb1e  pop     rbp
0x18003bb1f  retn
```
