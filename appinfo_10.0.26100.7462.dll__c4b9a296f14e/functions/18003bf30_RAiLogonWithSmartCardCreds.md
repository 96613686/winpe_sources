# RAiLogonWithSmartCardCreds

- ea: `0x18003bf30`
- end: `0x18003c061`
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
- `0x18003bf30`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003c00c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003c00c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bf8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bf8d`

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
                          &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
                          Reply);
  return result;
}

```

## disassembly

```asm
0x18003bf30  mov     r11, rsp
0x18003bf33  mov     [r11+8], rbx
0x18003bf37  mov     [r11+10h], rsi
0x18003bf3b  mov     [r11+18h], rdi
0x18003bf3f  push    rbp
0x18003bf40  mov     rbp, rsp
0x18003bf43  sub     rsp, 70h
0x18003bf47  and     [rbp+var_18], 0
0x18003bf4c  mov     rax, rdx
0x18003bf4f  and     [rbp+var_10], 0
0x18003bf54  lea     rdx, [rbp+var_8]; void **
0x18003bf58  and     [rbp+var_1C], 0
0x18003bf5c  mov     rsi, r9
0x18003bf5f  and     qword ptr [r11-58h], 0
0x18003bf64  lea     r9, [rbp+var_1C]; unsigned int *
0x18003bf68  mov     ebx, r8d
0x18003bf6b  mov     rdi, rcx
0x18003bf6e  mov     rcx, rax; void *
0x18003bf71  lea     r8, [rbp+var_18]; void **
0x18003bf75  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18003bf7a  mov     [rbp+Reply], eax
0x18003bf7d  test    eax, eax
0x18003bf7f  jnz     loc_18003C005
0x18003bf85  mov     edx, 0D0h; uBytes
0x18003bf8a  lea     ecx, [rax+40h]; uFlags
0x18003bf8d  call    cs:__imp_LocalAlloc
0x18003bf94  nop     dword ptr [rax+rax+00h]
0x18003bf99  mov     rdx, rax
0x18003bf9c  test    rax, rax
0x18003bf9f  jnz     short loc_18003BFAA
0x18003bfa1  mov     [rbp+Reply], 8
0x18003bfa8  jmp     short loc_18003C005
0x18003bfaa  mov     dword ptr [rax], 0D0h
0x18003bfb0  mov     dword ptr [rax+4], 4
0x18003bfb7  mov     dword ptr [rax+0C8h], 1
0x18003bfc1  mov     r9, [rbp+arg_20]
0x18003bfc5  lea     rax, [rbp+var_10]
0x18003bfc9  mov     rcx, [rbp+var_18]
0x18003bfcd  and     ebx, 10h
0x18003bfd0  mov     [rsp+70h+var_28], rax
0x18003bfd5  bts     ebx, 0Bh
0x18003bfd9  and     [rsp+70h+var_30], 0
0x18003bfdf  mov     r8, rsi
0x18003bfe2  or      [rsp+70h+var_38], 0FFFFFFFFh
0x18003bfe7  mov     eax, [rbp+var_1C]
0x18003bfea  shl     ebx, 7
0x18003bfed  mov     [rsp+70h+var_40], 6
0x18003bff5  mov     [rsp+70h+var_48], ebx
0x18003bff9  mov     [rsp+70h+var_50], eax
0x18003bffd  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18003c002  mov     [rbp+Reply], eax
0x18003c005  lea     rdx, [rbp+Reply]; Reply
0x18003c009  mov     rcx, rdi; pAsync
0x18003c00c  call    cs:__imp_RpcAsyncCompleteCall
0x18003c013  nop     dword ptr [rax+rax+00h]
0x18003c018  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c01f  lea     rax, WPP_GLOBAL_Control
0x18003c026  cmp     rcx, rax
0x18003c029  jz      short loc_18003C04A
0x18003c02b  test    byte ptr [rcx+1Ch], 1
0x18003c02f  jz      short loc_18003C04A
0x18003c031  mov     r9d, [rbp+Reply]
0x18003c035  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x18003c03c  mov     rcx, [rcx+10h]
0x18003c040  mov     edx, 0Ah
0x18003c045  call    WPP_SF_D
0x18003c04a  lea     r11, [rsp+70h+var_s0]
0x18003c04f  mov     rbx, [r11+10h]
0x18003c053  mov     rsi, [r11+18h]
0x18003c057  mov     rdi, [r11+20h]
0x18003c05b  mov     rsp, r11
0x18003c05e  pop     rbp
0x18003c05f  retn
```
