# RAiLogonWithSmartCardCreds

- ea: `0x18003adb0`
- end: `0x18003aee1`
- name: `RAiLogonWithSmartCardCreds`
- size: `305`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a230`
- `0x180024db0`
- `0x1800263a8`
- `0x18003adb0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ae8c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ae8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ae0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ae0d`

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
                          &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18003adb0  mov     r11, rsp
0x18003adb3  mov     [r11+8], rbx
0x18003adb7  mov     [r11+10h], rsi
0x18003adbb  mov     [r11+18h], rdi
0x18003adbf  push    rbp
0x18003adc0  mov     rbp, rsp
0x18003adc3  sub     rsp, 70h
0x18003adc7  and     [rbp+var_18], 0
0x18003adcc  mov     rax, rdx
0x18003adcf  and     [rbp+var_10], 0
0x18003add4  lea     rdx, [rbp+var_8]; void **
0x18003add8  and     [rbp+var_1C], 0
0x18003addc  mov     rsi, r9
0x18003addf  and     qword ptr [r11-58h], 0
0x18003ade4  lea     r9, [rbp+var_1C]; unsigned int *
0x18003ade8  mov     ebx, r8d
0x18003adeb  mov     rdi, rcx
0x18003adee  mov     rcx, rax; void *
0x18003adf1  lea     r8, [rbp+var_18]; void **
0x18003adf5  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003adfa  mov     [rbp+Reply], eax
0x18003adfd  test    eax, eax
0x18003adff  jnz     loc_18003AE85
0x18003ae05  mov     edx, 0D0h; uBytes
0x18003ae0a  lea     ecx, [rax+40h]; uFlags
0x18003ae0d  call    cs:__imp_LocalAlloc
0x18003ae14  nop     dword ptr [rax+rax+00h]
0x18003ae19  mov     rdx, rax
0x18003ae1c  test    rax, rax
0x18003ae1f  jnz     short loc_18003AE2A
0x18003ae21  mov     [rbp+Reply], 8
0x18003ae28  jmp     short loc_18003AE85
0x18003ae2a  mov     dword ptr [rax], 0D0h
0x18003ae30  mov     dword ptr [rax+4], 4
0x18003ae37  mov     dword ptr [rax+0C8h], 1
0x18003ae41  mov     r9, [rbp+arg_20]
0x18003ae45  lea     rax, [rbp+var_10]
0x18003ae49  mov     rcx, [rbp+var_18]
0x18003ae4d  and     ebx, 10h
0x18003ae50  mov     [rsp+70h+var_28], rax
0x18003ae55  bts     ebx, 0Bh
0x18003ae59  and     [rsp+70h+var_30], 0
0x18003ae5f  mov     r8, rsi
0x18003ae62  or      [rsp+70h+var_38], 0FFFFFFFFh
0x18003ae67  mov     eax, [rbp+var_1C]
0x18003ae6a  shl     ebx, 7
0x18003ae6d  mov     [rsp+70h+var_40], 6
0x18003ae75  mov     [rsp+70h+var_48], ebx
0x18003ae79  mov     [rsp+70h+var_50], eax
0x18003ae7d  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18003ae82  mov     [rbp+Reply], eax
0x18003ae85  lea     rdx, [rbp+Reply]; Reply
0x18003ae89  mov     rcx, rdi; pAsync
0x18003ae8c  call    cs:__imp_RpcAsyncCompleteCall
0x18003ae93  nop     dword ptr [rax+rax+00h]
0x18003ae98  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae9f  lea     rax, WPP_GLOBAL_Control
0x18003aea6  cmp     rcx, rax
0x18003aea9  jz      short loc_18003AECA
0x18003aeab  test    byte ptr [rcx+1Ch], 1
0x18003aeaf  jz      short loc_18003AECA
0x18003aeb1  mov     r9d, [rbp+Reply]
0x18003aeb5  lea     r8, WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids
0x18003aebc  mov     rcx, [rcx+10h]
0x18003aec0  mov     edx, 0Ah
0x18003aec5  call    WPP_SF_D
0x18003aeca  lea     r11, [rsp+70h+var_s0]
0x18003aecf  mov     rbx, [r11+10h]
0x18003aed3  mov     rsi, [r11+18h]
0x18003aed7  mov     rdi, [r11+20h]
0x18003aedb  mov     rsp, r11
0x18003aede  pop     rbp
0x18003aedf  retn
```
