# BfAddCloudFileECPs

- ea: `0x140011eb0`
- end: `0x140011fae`
- name: `BfAddCloudFileECPs`
- size: `254`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140002904`

## callees

- `0x140001348`
- `0x140011eb0`
- `0x140011fb4`
- `0x1400123dc`

## import_xrefs

- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140011ed7`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140011ed7`

## pseudocode

```c
__int64 __fastcall BfAddCloudFileECPs(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        __int64 a3,
        _BYTE *a4,
        _BYTE *a5,
        _BYTE *a6)
{
  struct _ECP_LIST **v6; // rdi
  int ParameterList; // ebx
  int v11; // edx
  int v12; // r9d
  char v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+38h] [rbp-30h]

  v6 = (struct _ECP_LIST **)(a3 + 8);
  if ( !*(_QWORD *)(a3 + 8) )
  {
    ParameterList = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)(a2 + 8), 0, (PECP_LIST *)(a3 + 8));
    if ( ParameterList < 0 )
      return (unsigned int)ParameterList;
    *a4 = 1;
  }
  ParameterList = BfAttachRedirHandleCollapseEcp(a2, *v6, a5);
  if ( ParameterList >= 0 )
  {
    ParameterList = BfAttachAttributionInformationEcp(CallbackData, a2, *v6, a6);
    if ( ParameterList < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = ParameterList;
      v12 = 11;
      v14 = -70;
      goto LABEL_10;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = ParameterList;
    v12 = 10;
    v14 = -81;
LABEL_10:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      5,
      v12,
      (__int64)WPP_a1f8eef2b6bd307feb01db48b2c70615_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\sfo.c",
      v14,
      v15);
  }
  return (unsigned int)ParameterList;
}

```

## disassembly

```asm
0x140011eb0  push    rbx
0x140011eb2  push    rbp
0x140011eb3  push    rsi
0x140011eb4  push    rdi
0x140011eb5  push    r14
0x140011eb7  sub     rsp, 40h
0x140011ebb  lea     rdi, [r8+8]
0x140011ebf  mov     r14, r9
0x140011ec2  cmp     qword ptr [rdi], 0
0x140011ec6  mov     rsi, rdx
0x140011ec9  mov     rbp, rcx
0x140011ecc  jnz     short loc_140011EF1
0x140011ece  mov     rcx, [rsi+8]; Filter
0x140011ed2  mov     r8, rdi; EcpList
0x140011ed5  xor     edx, edx; Flags
0x140011ed7  call    cs:__imp_FltAllocateExtraCreateParameterList
0x140011ede  nop     dword ptr [rax+rax+00h]
0x140011ee3  mov     ebx, eax
0x140011ee5  test    eax, eax
0x140011ee7  js      loc_140011FA0
0x140011eed  mov     byte ptr [r14], 1
0x140011ef1  mov     r8, [rsp+68h+arg_20]
0x140011ef9  mov     rcx, rsi
0x140011efc  mov     rdx, [rdi]
0x140011eff  call    BfAttachRedirHandleCollapseEcp
0x140011f04  mov     ebx, eax
0x140011f06  test    eax, eax
0x140011f08  jns     short loc_140011F32
0x140011f0a  lea     rax, WPP_RECORDER_INITIALIZED
0x140011f11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011f18  jz      loc_140011FA0
0x140011f1e  mov     [rsp+68h+var_30], ebx
0x140011f22  mov     r9d, 0Ah
0x140011f28  mov     dword ptr [rsp+68h+var_38], 1AFh
0x140011f30  jmp     short loc_140011F70
0x140011f32  mov     r9, [rsp+68h+arg_28]
0x140011f3a  mov     rdx, rsi
0x140011f3d  mov     r8, [rdi]
0x140011f40  mov     rcx, rbp; CallbackData
0x140011f43  call    BfAttachAttributionInformationEcp
0x140011f48  mov     ebx, eax
0x140011f4a  test    eax, eax
0x140011f4c  jns     short loc_140011FA0
0x140011f4e  lea     rax, WPP_RECORDER_INITIALIZED
0x140011f55  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011f5c  jz      short loc_140011FA0
0x140011f5e  mov     [rsp+68h+var_30], ebx
0x140011f62  mov     r9d, 0Bh
0x140011f68  mov     dword ptr [rsp+68h+var_38], 1BAh
0x140011f70  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f77  lea     rax, aOnecoreBaseFsW_5; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140011f7e  mov     [rsp+68h+var_40], rax
0x140011f83  mov     r8d, 5
0x140011f89  lea     rax, WPP_a1f8eef2b6bd307feb01db48b2c70615_Traceguids
0x140011f90  mov     dl, 2
0x140011f92  mov     [rsp+68h+var_48], rax
0x140011f97  mov     rcx, [rcx+40h]
0x140011f9b  call    WPP_RECORDER_SF_sDd
0x140011fa0  mov     eax, ebx
0x140011fa2  add     rsp, 40h
0x140011fa6  pop     r14
0x140011fa8  pop     rdi
0x140011fa9  pop     rsi
0x140011faa  pop     rbp
0x140011fab  pop     rbx
0x140011fac  retn
```
