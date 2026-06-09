# AuthHostWebInstance::TerminateNavigate(ushort const *,ulong)

- ea: `0x14000b840`
- end: `0x14000bb15`
- name: `?TerminateNavigate@AuthHostWebInstance@@AEAAXPEBGK@Z`
- size: `725`
- prototype: `void __fastcall(AuthHostWebInstance *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140007bd0`
- `0x1400096cc`
- `0x1400097b0`
- `0x140009988`
- `0x14000aa60`
- `0x14000b0d0`

## callees

- `0x140002c98`
- `0x1400066dc`
- `0x140006748`
- `0x1400091b8`
- `0x140009214`
- `0x140009b84`
- `0x14000b840`
- `0x14000c45c`
- `0x14000c4f8`
- `0x14000c9c8`
- `0x14000cbf4`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostQuitMessage` at `0x14000b9be`
- `ext-ms-win-ntuser-message-l1-1-0!PostQuitMessage` at `0x14000b9be`

## pseudocode

```c
void __fastcall AuthHostWebInstance::TerminateNavigate(AuthHostWebInstance *this, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // edi
  PVOID v9; // rcx
  unsigned int AuthHostPageStateString; // eax
  __int64 v11; // rcx
  int v12; // r8d
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // edi
  unsigned int v16; // ebp
  unsigned int v17; // r15d
  __int64 v18; // rcx
  __int64 v19; // r10
  int v20; // eax
  __int64 v21; // r10
  __int64 v22; // rcx
  int v23; // eax
  _QWORD v24[4]; // [rsp+40h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+60h] [rbp-58h] BYREF

  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v24, a2);
  v8 = *((_DWORD *)this + 33);
  if ( a3 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      AuthHostPageStateString = (unsigned int)AuthHostWebInstance::GetAuthHostPageStateString(
                                                (__int64)WPP_GLOBAL_Control,
                                                v8);
      WPP_SF_SDdS(*(_QWORD *)(v11 + 56), 64, v12, AuthHostPageStateString, a3, a3, (__int64)a2);
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v13 = (unsigned int)AuthHostWebInstance::GetAuthHostPageStateString((__int64)WPP_GLOBAL_Control, v8);
      WPP_SF_SS(
        *(_QWORD *)(v14 + 56),
        65,
        (unsigned int)&WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
        v13,
        (__int64)a2);
    }
  }
  if ( ((v8 - 3) & 0xFFFFFFFD) != 0 )
  {
    if ( (unsigned int)(a3 - 400) > 0xC7 )
    {
      if ( a3 == 1223 )
      {
        v16 = 1;
        if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            (__int64)v9,
            (const EVENT_DESCRIPTOR *)NavigateCancelledEvent,
            v7,
            1u,
            &v25);
        *(_QWORD *)((char *)this + 508) = 0;
        v15 = 0;
        v17 = 0;
        goto LABEL_16;
      }
      v15 = 0;
      v17 = 0;
      v16 = 0;
      if ( !a3 )
        goto LABEL_16;
      if ( a2 && *a2 && (Microsoft_Windows_WebAuthEnableBits & 2) != 0 )
        McTemplateU0zd_EventWriteTransfer((__int64)v9, (const EVENT_DESCRIPTOR *)NavigateErrorEvent, a2, a3);
      if ( a3 > 0 )
        v15 = (unsigned __int16)a3 | 0x80070000;
      else
        v15 = a3;
    }
    else
    {
      if ( (Microsoft_Windows_WebAuthEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer((__int64)v9, v6, a2, a3);
      v15 = 0;
      v16 = 2;
      v17 = a3;
      if ( !a3 || a3 == 1223 )
        goto LABEL_16;
    }
    if ( (*((_DWORD *)this + 32) & 0x20000) == 0 && !(unsigned int)GetAuthHostRegDWORDValue(L"DisableErrorPage") )
    {
      v21 = *((_QWORD *)this + 13);
      v22 = v24[0];
      *((_DWORD *)this + 33) = 3;
      *(_QWORD *)((char *)this + 508) = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v21 + 80LL))(
              v21,
              v15,
              v16,
              v17,
              v22);
      if ( v23 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x42u, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v23);
      }
      AuthHostWebInstance::NavigateToAuthHostPage(this, 4);
      return;
    }
LABEL_16:
    v18 = *((_QWORD *)this + 13);
    v19 = v24[0];
    *((_DWORD *)this + 33) = 5;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v18 + 72LL))(
            v18,
            v15,
            v16,
            v17,
            v19);
    if ( v20 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x43u, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v20);
    }
    PostQuitMessage(0);
  }
}

```

## disassembly

```asm
0x14000b840  mov     [rsp+arg_18], rbx
0x14000b845  push    rbp
0x14000b846  push    rsi
0x14000b847  push    rdi
0x14000b848  push    r12
0x14000b84a  push    r13
0x14000b84c  push    r14
0x14000b84e  push    r15
0x14000b850  sub     rsp, 80h
0x14000b857  mov     rax, cs:__security_cookie
0x14000b85e  xor     rax, rsp
0x14000b861  mov     [rsp+0B8h+var_48], rax
0x14000b866  mov     rsi, rcx
0x14000b869  mov     ebx, r8d
0x14000b86c  lea     rcx, [rsp+0B8h+var_78]; this
0x14000b871  mov     r14, rdx
0x14000b874  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x14000b879  mov     edi, [rsi+84h]
0x14000b87f  xor     r13d, r13d
0x14000b882  test    ebx, ebx
0x14000b884  jz      short loc_14000B8CB
0x14000b886  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b88d  lea     r12, WPP_GLOBAL_Control
0x14000b894  cmp     rcx, r12
0x14000b897  jz      short loc_14000B90E
0x14000b899  test    byte ptr [rcx+44h], 4
0x14000b89d  jz      short loc_14000B90E
0x14000b89f  cmp     byte ptr [rcx+41h], 2
0x14000b8a3  jb      short loc_14000B90E
0x14000b8a5  mov     edx, edi
0x14000b8a7  call    ?GetAuthHostPageStateString@AuthHostWebInstance@@AEAAPEBGW4AuthHostPageState@1@@Z; AuthHostWebInstance::GetAuthHostPageStateString(AuthHostWebInstance::AuthHostPageState)
0x14000b8ac  mov     rcx, [rcx+38h]
0x14000b8b0  lea     edx, [r13+40h]
0x14000b8b4  mov     [rsp+0B8h+var_88], r14
0x14000b8b9  mov     r9, rax
0x14000b8bc  mov     [rsp+0B8h+var_90], ebx
0x14000b8c0  mov     dword ptr [rsp+0B8h+var_98], ebx
0x14000b8c4  call    WPP_SF_SDdS
0x14000b8c9  jmp     short loc_14000B90E
0x14000b8cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8d2  lea     r12, WPP_GLOBAL_Control
0x14000b8d9  cmp     rcx, r12
0x14000b8dc  jz      short loc_14000B90E
0x14000b8de  test    byte ptr [rcx+44h], 4
0x14000b8e2  jz      short loc_14000B90E
0x14000b8e4  cmp     byte ptr [rcx+41h], 4
0x14000b8e8  jb      short loc_14000B90E
0x14000b8ea  mov     edx, edi
0x14000b8ec  call    ?GetAuthHostPageStateString@AuthHostWebInstance@@AEAAPEBGW4AuthHostPageState@1@@Z; AuthHostWebInstance::GetAuthHostPageStateString(AuthHostWebInstance::AuthHostPageState)
0x14000b8f1  mov     rcx, [rcx+38h]
0x14000b8f5  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b8fc  mov     r9, rax
0x14000b8ff  mov     [rsp+0B8h+var_98], r14
0x14000b904  mov     edx, 41h ; 'A'
0x14000b909  call    WPP_SF_SS
0x14000b90e  lea     eax, [rdi-3]
0x14000b911  test    eax, 0FFFFFFFDh
0x14000b916  jz      loc_14000B9C4
0x14000b91c  lea     eax, [rbx-190h]
0x14000b922  cmp     eax, 0C7h
0x14000b927  ja      loc_14000B9EC
0x14000b92d  test    cs:Microsoft_Windows_WebAuthEnableBits, 2
0x14000b934  jz      short loc_14000B941
0x14000b936  mov     r9d, ebx
0x14000b939  mov     r8, r14
0x14000b93c  call    McTemplateU0zq_EventWriteTransfer
0x14000b941  mov     edi, r13d
0x14000b944  mov     ebp, 2
0x14000b949  mov     r15d, ebx
0x14000b94c  test    ebx, ebx
0x14000b94e  jz      short loc_14000B95C
0x14000b950  cmp     ebx, 4C7h
0x14000b956  jnz     loc_14000BA75
0x14000b95c  mov     rcx, [rsi+68h]
0x14000b960  mov     r9d, r15d
0x14000b963  mov     r10, [rsp+0B8h+var_78]
0x14000b968  mov     r8d, ebp
0x14000b96b  mov     dword ptr [rsi+84h], 5
0x14000b975  mov     edx, edi
0x14000b977  mov     [rsp+0B8h+var_98], r10
0x14000b97c  mov     rax, [rcx]
0x14000b97f  mov     rax, [rax+48h]
0x14000b983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b988  test    eax, eax
0x14000b98a  jns     short loc_14000B9BC
0x14000b98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b993  cmp     rcx, r12
0x14000b996  jz      short loc_14000B9BC
0x14000b998  test    byte ptr [rcx+44h], 4
0x14000b99c  jz      short loc_14000B9BC
0x14000b99e  cmp     byte ptr [rcx+41h], 2
0x14000b9a2  jb      short loc_14000B9BC
0x14000b9a4  mov     rcx, [rcx+38h]
0x14000b9a8  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b9af  mov     edx, 43h ; 'C'
0x14000b9b4  mov     r9d, eax
0x14000b9b7  call    WPP_SF_d
0x14000b9bc  xor     ecx, ecx; nExitCode
0x14000b9be  call    cs:__imp_PostQuitMessage
0x14000b9c4  mov     rcx, [rsp+0B8h+var_48]
0x14000b9c9  xor     rcx, rsp; StackCookie
0x14000b9cc  call    __security_check_cookie
0x14000b9d1  mov     rbx, [rsp+0B8h+arg_18]
0x14000b9d9  add     rsp, 80h
0x14000b9e0  pop     r15
0x14000b9e2  pop     r14
0x14000b9e4  pop     r13
0x14000b9e6  pop     r12
0x14000b9e8  pop     rdi
0x14000b9e9  pop     rsi
0x14000b9ea  pop     rbp
0x14000b9eb  retn
0x14000b9ec  cmp     ebx, 4C7h
0x14000b9f2  jnz     short loc_14000BA2D
0x14000b9f4  mov     ebp, 1
0x14000b9f9  test    cs:Microsoft_Windows_WebAuthEnableBits, bpl
0x14000ba00  jz      short loc_14000BA1B
0x14000ba02  lea     rax, [rsp+0B8h+var_58]
0x14000ba07  mov     r9d, ebp
0x14000ba0a  lea     rdx, NavigateCancelledEvent
0x14000ba11  mov     [rsp+0B8h+var_98], rax
0x14000ba16  call    McGenEventWrite_EventWriteTransfer
0x14000ba1b  mov     [rsi+1FCh], r13
0x14000ba22  mov     edi, r13d
0x14000ba25  mov     r15d, r13d
0x14000ba28  jmp     loc_14000B95C
0x14000ba2d  mov     edi, r13d
0x14000ba30  mov     r15d, r13d
0x14000ba33  mov     ebp, r13d
0x14000ba36  test    ebx, ebx
0x14000ba38  jz      loc_14000B95C
0x14000ba3e  test    r14, r14
0x14000ba41  jz      short loc_14000BA64
0x14000ba43  cmp     [r14], r13w
0x14000ba47  jz      short loc_14000BA64
0x14000ba49  test    cs:Microsoft_Windows_WebAuthEnableBits, 2
0x14000ba50  jz      short loc_14000BA64
0x14000ba52  mov     r9d, ebx
0x14000ba55  lea     rdx, NavigateErrorEvent
0x14000ba5c  mov     r8, r14
0x14000ba5f  call    McTemplateU0zd_EventWriteTransfer
0x14000ba64  test    ebx, ebx
0x14000ba66  jg      short loc_14000BA6C
0x14000ba68  mov     edi, ebx
0x14000ba6a  jmp     short loc_14000BA75
0x14000ba6c  movzx   edi, bx
0x14000ba6f  or      edi, 80070000h
0x14000ba75  test    dword ptr [rsi+80h], 20000h
0x14000ba7f  jnz     loc_14000B95C
0x14000ba85  lea     rcx, aDisableerrorpa; "DisableErrorPage"
0x14000ba8c  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x14000ba91  test    eax, eax
0x14000ba93  jnz     loc_14000B95C
0x14000ba99  mov     r10, [rsi+68h]
0x14000ba9d  mov     r9d, r15d
0x14000baa0  mov     rcx, [rsp+0B8h+var_78]
0x14000baa5  mov     r8d, ebp
0x14000baa8  mov     dword ptr [rsi+84h], 3
0x14000bab2  mov     edx, edi
0x14000bab4  mov     [rsi+1FCh], r13
0x14000babb  mov     rax, [r10]
0x14000babe  mov     [rsp+0B8h+var_98], rcx
0x14000bac3  mov     rcx, r10
0x14000bac6  mov     rax, [rax+50h]
0x14000baca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bacf  test    eax, eax
0x14000bad1  jns     short loc_14000BB03
0x14000bad3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bada  cmp     rcx, r12
0x14000badd  jz      short loc_14000BB03
0x14000badf  test    byte ptr [rcx+44h], 4
0x14000bae3  jz      short loc_14000BB03
0x14000bae5  cmp     byte ptr [rcx+41h], 2
0x14000bae9  jb      short loc_14000BB03
0x14000baeb  mov     rcx, [rcx+38h]
0x14000baef  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000baf6  mov     edx, 42h ; 'B'
0x14000bafb  mov     r9d, eax
0x14000bafe  call    WPP_SF_d
0x14000bb03  mov     edx, 4
0x14000bb08  mov     rcx, rsi
0x14000bb0b  call    ?NavigateToAuthHostPage@AuthHostWebInstance@@AEAAXW4AuthHostPageState@1@@Z; AuthHostWebInstance::NavigateToAuthHostPage(AuthHostWebInstance::AuthHostPageState)
0x14000bb10  jmp     loc_14000B9C4
```
