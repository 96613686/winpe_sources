# KapiProcessUpdateRequest

- ea: `0x180006eb0`
- end: `0x180007236`
- name: `KapiProcessUpdateRequest`
- size: `902`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008140`
- `0x18000f920`
- `0x18002cc7c`

## callees

- `0x1800030b0`
- `0x180003ed0`
- `0x180005c7c`
- `0x180006eb0`
- `0x1800098f0`
- `0x18000a160`
- `0x18001002c`
- `0x1800100d0`
- `0x180010168`
- `0x1800154f4`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f59`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006f9f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180006f9f`

## pseudocode

```c
__int64 __fastcall KapiProcessUpdateRequest(LPVOID lpMem)
{
  __int64 SignatureNetworkGuids; // rsi
  __int64 v3; // r14
  int v4; // r12d
  int v5; // r13d
  __int64 v6; // r15
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int *v12; // rdi
  __int64 result; // rax
  __int64 v14; // rcx
  int Reply; // [rsp+30h] [rbp-A9h] BYREF
  int v16; // [rsp+38h] [rbp-A1h] BYREF
  int v17; // [rsp+40h] [rbp-99h] BYREF
  int v18; // [rsp+48h] [rbp-91h] BYREF
  __int64 v19; // [rsp+50h] [rbp-89h] BYREF
  LPVOID v20; // [rsp+58h] [rbp-81h] BYREF
  __int64 v21; // [rsp+60h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+70h] [rbp-69h] BYREF
  __int64 *v23; // [rsp+80h] [rbp-59h]
  __int64 v24; // [rsp+88h] [rbp-51h]
  LPVOID *v25; // [rsp+90h] [rbp-49h]
  __int64 v26; // [rsp+98h] [rbp-41h]
  int *v27; // [rsp+A0h] [rbp-39h]
  __int64 v28; // [rsp+A8h] [rbp-31h]
  int *v29; // [rsp+B0h] [rbp-29h]
  __int64 v30; // [rsp+B8h] [rbp-21h]
  __int64 *v31; // [rsp+C0h] [rbp-19h]
  __int64 v32; // [rsp+C8h] [rbp-11h]
  int *v33; // [rsp+D0h] [rbp-9h]
  __int64 v34; // [rsp+D8h] [rbp-1h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  SignatureNetworkGuids = 0;
  Reply = 0;
  v3 = 0;
  v4 = 60;
  v5 = -1;
  EnterCriticalSection(&g_KapiProviderSetLock);
  if ( g_KapiInitialized )
  {
    if ( g_KapiNlmSignature )
    {
      if ( (unsigned int)StubNlmCacheIsSignatureStable() )
      {
        SignatureNetworkGuids = StubNlmCacheGetSignatureNetworkGuids();
        if ( SignatureNetworkGuids )
        {
          v3 = CopySampleSetHelper(g_KapiKaSampleSet);
          if ( !v3 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
            }
            StubNlmCacheFreeNetworkGuids(g_KapiNlmCache, SignatureNetworkGuids);
            SignatureNetworkGuids = 0;
          }
        }
      }
    }
  }
  else
  {
    Reply = 1255;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 1255);
    }
  }
  v6 = g_KapiNlmEpoch;
  LeaveCriticalSection(&g_KapiProviderSetLock);
  v7 = (_QWORD *)*((_QWORD *)lpMem + 3);
  *v7 = CopyNetworkGuidListHelper(SignatureNetworkGuids);
  **((_QWORD **)lpMem + 4) = v3;
  **((_QWORD **)lpMem + 2) = v6;
  if ( v3 )
  {
    v10 = *(_QWORD *)(v3 + 16);
    v4 = *(_DWORD *)(v10 + 20);
    v5 = *(_DWORD *)(v10 + 16);
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v18 = Reply;
    v19 = *((_QWORD *)lpMem + 6);
    v23 = &v19;
    v25 = &v20;
    v27 = &v16;
    v29 = &v17;
    v31 = &v21;
    v33 = &v18;
    v21 = v6;
    v17 = v5;
    v16 = v4;
    v20 = lpMem;
    v24 = 8;
    v26 = 8;
    v28 = 4;
    v30 = 4;
    v32 = 8;
    v34 = 4;
    McGenEventWrite_EventWriteTransfer(
      v8,
      (const EVENT_DESCRIPTOR *)NcbKapiReceiveKaUpdateRequestCompletion,
      v9,
      7u,
      &v22);
  }
  v11 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)lpMem + 5), &Reply);
  if ( v11
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, v11);
  }
  v12 = (unsigned int *)*((_QWORD *)lpMem + 6);
  result = VpnFree(lpMem);
  if ( v12 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0pqsq_EventWriteTransfer(v14, NcbKapiProviderDereference, v12, v12[4]);
    result = KapiDereferenceProviderEx(v12);
  }
  if ( SignatureNetworkGuids )
    result = StubNlmCacheFreeNetworkGuids(g_KapiNlmCache, SignatureNetworkGuids);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180006eb0  push    rbp
0x180006eb2  push    rbx
0x180006eb3  push    rsi
0x180006eb4  push    rdi
0x180006eb5  push    r12
0x180006eb7  push    r13
0x180006eb9  push    r14
0x180006ebb  push    r15
0x180006ebd  lea     rbp, [rsp-1Fh]
0x180006ec2  sub     rsp, 0F8h
0x180006ec9  mov     rax, cs:__security_cookie
0x180006ed0  xor     rax, rsp
0x180006ed3  mov     [rbp+57h+var_50], rax
0x180006ed7  mov     rbx, rcx
0x180006eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ee1  lea     rdi, WPP_GLOBAL_Control
0x180006ee8  cmp     rcx, rdi
0x180006eeb  jz      short loc_180006EF7
0x180006eed  test    byte ptr [rcx+1Ch], 2
0x180006ef1  jnz     loc_18000717E
0x180006ef7  xor     esi, esi
0x180006ef9  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x180006f00  mov     [rsp+130h+Reply], esi
0x180006f04  xor     r14d, r14d
0x180006f07  mov     r12d, 3Ch ; '<'
0x180006f0d  mov     r13d, 0FFFFFFFFh
0x180006f13  call    cs:__imp_EnterCriticalSection
0x180006f19  cmp     cs:g_KapiInitialized, esi
0x180006f1f  jz      loc_1800071A2
0x180006f25  mov     rcx, cs:g_KapiNlmSignature
0x180006f2c  test    rcx, rcx
0x180006f2f  jz      short loc_180006F4B
0x180006f31  call    StubNlmCacheIsSignatureStable
0x180006f36  test    eax, eax
0x180006f38  jz      short loc_180006F4B
0x180006f3a  call    StubNlmCacheGetSignatureNetworkGuids
0x180006f3f  mov     rsi, rax
0x180006f42  test    rax, rax
0x180006f45  jnz     loc_1800070EF
0x180006f4b  mov     r15, cs:g_KapiNlmEpoch
0x180006f52  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x180006f59  call    cs:__imp_LeaveCriticalSection
0x180006f5f  mov     rdi, [rbx+18h]
0x180006f63  mov     rcx, rsi
0x180006f66  call    CopyNetworkGuidListHelper
0x180006f6b  mov     [rdi], rax
0x180006f6e  mov     rax, [rbx+20h]
0x180006f72  mov     [rax], r14
0x180006f75  mov     rax, [rbx+10h]
0x180006f79  mov     [rax], r15
0x180006f7c  test    r14, r14
0x180006f7f  jz      short loc_180006F8D
0x180006f81  mov     rax, [r14+10h]
0x180006f85  mov     r12d, [rax+14h]
0x180006f89  mov     r13d, [rax+10h]
0x180006f8d  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180006f94  jnz     short loc_180007002
0x180006f96  mov     rcx, [rbx+28h]; pAsync
0x180006f9a  lea     rdx, [rsp+130h+Reply]; Reply
0x180006f9f  call    cs:__imp_RpcAsyncCompleteCall
0x180006fa5  test    eax, eax
0x180006fa7  jnz     loc_1800071EE
0x180006fad  lea     r14, WPP_GLOBAL_Control
0x180006fb4  mov     rdi, [rbx+30h]
0x180006fb8  mov     rcx, rbx; lpMem
0x180006fbb  call    VpnFree
0x180006fc0  test    rdi, rdi
0x180006fc3  jnz     loc_1800070D9
0x180006fc9  test    rsi, rsi
0x180006fcc  jnz     loc_18000716A
0x180006fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd9  cmp     rcx, r14
0x180006fdc  jnz     loc_1800070AB
0x180006fe2  mov     rcx, [rbp+57h+var_50]
0x180006fe6  xor     rcx, rsp; StackCookie
0x180006fe9  call    __security_check_cookie
0x180006fee  add     rsp, 0F8h
0x180006ff5  pop     r15
0x180006ff7  pop     r14
0x180006ff9  pop     r13
0x180006ffb  pop     r12
0x180006ffd  pop     rdi
0x180006ffe  pop     rsi
0x180006fff  pop     rbx
0x180007000  pop     rbp
0x180007001  retn
0x180007002  mov     eax, [rsp+130h+Reply]
0x180007006  lea     rdx, NcbKapiReceiveKaUpdateRequestCompletion
0x18000700d  mov     [rsp+130h+var_E8], eax
0x180007011  mov     r9d, 7
0x180007017  mov     rax, [rbx+30h]
0x18000701b  mov     [rsp+130h+var_E0], rax
0x180007020  lea     rax, [rsp+130h+var_E0]
0x180007025  mov     [rbp+57h+var_B0], rax
0x180007029  lea     rax, [rsp+130h+var_D8]
0x18000702e  mov     [rbp+57h+var_A0], rax
0x180007032  lea     rax, [rsp+130h+var_F8]
0x180007037  mov     [rbp+57h+var_90], rax
0x18000703b  lea     rax, [rsp+130h+var_F0]
0x180007040  mov     [rbp+57h+var_80], rax
0x180007044  lea     rax, [rbp+57h+var_D0]
0x180007048  mov     [rbp+57h+var_70], rax
0x18000704c  lea     rax, [rsp+130h+var_E8]
0x180007051  mov     [rbp+57h+var_60], rax
0x180007055  lea     rax, [rbp+57h+var_C0]
0x180007059  mov     [rsp+130h+var_110], rax
0x18000705e  mov     [rbp+57h+var_D0], r15
0x180007062  mov     [rsp+130h+var_F0], r13d
0x180007067  mov     [rsp+130h+var_F8], r12d
0x18000706c  mov     [rsp+130h+var_D8], rbx
0x180007071  mov     [rbp+57h+var_A8], 8
0x180007079  mov     [rbp+57h+var_98], 8
0x180007081  mov     [rbp+57h+var_88], 4
0x180007089  mov     [rbp+57h+var_78], 4
0x180007091  mov     [rbp+57h+var_68], 8
0x180007099  mov     [rbp+57h+var_58], 4
0x1800070a1  call    McGenEventWrite_EventWriteTransfer
0x1800070a6  jmp     loc_180006F96
0x1800070ab  test    byte ptr [rcx+1Ch], 2
0x1800070af  jz      loc_180006FE2
0x1800070b5  cmp     byte ptr [rcx+19h], 6
0x1800070b9  jb      loc_180006FE2
0x1800070bf  mov     rcx, [rcx+10h]
0x1800070c3  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x1800070ca  mov     edx, 71h ; 'q'
0x1800070cf  call    WPP_SF_
0x1800070d4  jmp     loc_180006FE2
0x1800070d9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800070e0  jnz     short loc_18000714A
0x1800070e2  mov     rcx, rdi
0x1800070e5  call    KapiDereferenceProviderEx
0x1800070ea  jmp     loc_180006FC9
0x1800070ef  mov     rcx, cs:g_KapiKaSampleSet
0x1800070f6  call    CopySampleSetHelper
0x1800070fb  mov     r14, rax
0x1800070fe  test    rax, rax
0x180007101  jnz     loc_180006F4B
0x180007107  mov     rcx, cs:WPP_GLOBAL_Control
0x18000710e  cmp     rcx, rdi
0x180007111  jz      short loc_180007134
0x180007113  test    byte ptr [rcx+1Ch], 2
0x180007117  jz      short loc_180007134
0x180007119  cmp     byte ptr [rcx+19h], 5
0x18000711d  jb      short loc_180007134
0x18000711f  mov     rcx, [rcx+10h]
0x180007123  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000712a  mov     edx, 6Fh ; 'o'
0x18000712f  call    WPP_SF_
0x180007134  mov     rcx, cs:g_KapiNlmCache
0x18000713b  mov     rdx, rsi
0x18000713e  call    StubNlmCacheFreeNetworkGuids
0x180007143  xor     esi, esi
0x180007145  jmp     loc_180006F4B
0x18000714a  mov     r9d, [rdi+10h]
0x18000714e  lea     rdx, NcbKapiProviderDereference
0x180007155  mov     r8, rdi
0x180007158  mov     [rsp+130h+var_108], 56Eh
0x180007160  call    McTemplateU0pqsq_EventWriteTransfer
0x180007165  jmp     loc_1800070E2
0x18000716a  mov     rcx, cs:g_KapiNlmCache
0x180007171  mov     rdx, rsi
0x180007174  call    StubNlmCacheFreeNetworkGuids
0x180007179  jmp     loc_180006FD2
0x18000717e  cmp     byte ptr [rcx+19h], 6
0x180007182  jb      loc_180006EF7
0x180007188  mov     rcx, [rcx+10h]
0x18000718c  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x180007193  mov     edx, 6Dh ; 'm'
0x180007198  call    WPP_SF_
0x18000719d  jmp     loc_180006EF7
0x1800071a2  mov     [rsp+130h+Reply], 4E7h
0x1800071aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071b1  cmp     rcx, rdi
0x1800071b4  jz      loc_180006F4B
0x1800071ba  test    byte ptr [rcx+1Ch], 2
0x1800071be  jz      loc_180006F4B
0x1800071c4  cmp     byte ptr [rcx+19h], 2
0x1800071c8  jb      loc_180006F4B
0x1800071ce  mov     rcx, [rcx+10h]
0x1800071d2  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x1800071d9  mov     edx, 6Eh ; 'n'
0x1800071de  mov     r9d, 4E7h
0x1800071e4  call    WPP_SF_d
0x1800071e9  jmp     loc_180006F4B
0x1800071ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071f5  lea     r14, WPP_GLOBAL_Control
0x1800071fc  cmp     rcx, r14
0x1800071ff  jz      loc_180006FB4
0x180007205  test    byte ptr [rcx+1Ch], 2
0x180007209  jz      loc_180006FB4
0x18000720f  cmp     byte ptr [rcx+19h], 2
0x180007213  jb      loc_180006FB4
0x180007219  mov     rcx, [rcx+10h]
0x18000721d  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x180007224  mov     edx, 70h ; 'p'
0x180007229  mov     r9d, eax
0x18000722c  call    WPP_SF_d
0x180007231  jmp     loc_180006FB4
```
