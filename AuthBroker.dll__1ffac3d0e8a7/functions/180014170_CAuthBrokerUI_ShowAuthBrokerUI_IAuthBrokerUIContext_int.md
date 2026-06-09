# CAuthBrokerUI::ShowAuthBrokerUI(IAuthBrokerUIContext *,int)

- ea: `0x180014170`
- end: `0x1800142d3`
- name: `?ShowAuthBrokerUI@CAuthBrokerUI@@EEAAJPEAUIAuthBrokerUIContext@@H@Z`
- size: `355`
- prototype: `__int64 __fastcall(CAuthBrokerUI *this, IAuthBrokerUIContext *puiContext, int fInProcActivation)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000737c`
- `0x1800090e8`
- `0x180014170`
- `0x18001449c`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIUnInitProc` at `0x1800142c2`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIUnInitProc` at `0x1800142c2`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIUnInitThread` at `0x1800142af`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIUnInitThread` at `0x1800142af`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIInitProc` at `0x18001418e`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIInitProc` at `0x18001418e`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIInitThread` at `0x1800141db`
- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIInitThread` at `0x1800141db`

## pseudocode

```c
__int64 __fastcall CAuthBrokerUI::ShowAuthBrokerUI(
        CAuthBrokerUI *this,
        IAuthBrokerUIContext *puiContext,
        int fInProcActivation)
{
  unsigned int v5; // ebp
  signed int v6; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v7; // rax
  unsigned __int16 v8; // dx
  int v9; // eax
  unsigned __int64 Logger; // rcx
  unsigned __int16 v11; // dx
  unsigned int v12; // r9d

  v5 = 0;
  if ( IsDirectUIUnInitThreadPresent() )
  {
    v6 = DirectUIInitProc();
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v8 = 60;
LABEL_23:
        WPP_SF_d(v7[1].Control.Logger, v8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v6);
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    if ( IsDirectUIUnInitThreadPresent() )
    {
      v9 = DirectUIInitThread(65538);
      if ( v9 >= 0 )
      {
        v5 = ActivateAppContainerWorker(puiContext, fInProcActivation);
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        Logger = WPP_GLOBAL_Control[1].Control.Logger;
        v11 = 62;
        v12 = v9;
LABEL_18:
        WPP_SF_d(Logger, v11, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v12);
      }
    }
    else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
           && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
           && WPP_GLOBAL_Control[1].Control.Level >= 2u )
    {
      Logger = WPP_GLOBAL_Control[1].Control.Logger;
      v11 = 61;
      v12 = -2147467263;
      goto LABEL_18;
    }
LABEL_27:
    if ( IsDirectUIUnInitThreadPresent() )
      DirectUIUnInitProc();
    return v5;
  }
  v6 = -2147467263;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    v8 = 59;
    goto LABEL_23;
  }
LABEL_24:
  if ( IsDirectUIUnInitThreadPresent() )
    DirectUIUnInitThread();
  if ( v6 >= 0 )
    goto LABEL_27;
  return v5;
}

```

## disassembly

```asm
0x180014170  push    rbx
0x180014172  push    rbp
0x180014173  push    rsi
0x180014174  push    rdi
0x180014175  sub     rsp, 28h
0x180014179  mov     edi, fInProcActivation
0x18001417c  mov     rsi, puiContext
0x18001417f  xor     ebp, ebp
0x180014181  call    IsDirectUIUnInitThreadPresent
0x180014186  test    al, al
0x180014188  jz      loc_18001426A
0x18001418e  call    cs:__imp_DirectUIInitProc
0x180014194  mov     ebx, eax
0x180014196  test    eax, eax
0x180014198  jns     short loc_1800141CD
0x18001419a  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800141a1  lea     this, WPP_GLOBAL_Control
0x1800141a8  cmp     rax, this
0x1800141ab  jz      loc_1800142A6
0x1800141b1  test    byte ptr [rax+44h], 8
0x1800141b5  jz      loc_1800142A6
0x1800141bb  cmp     byte ptr [rax+41h], 2
0x1800141bf  jb      loc_1800142A6
0x1800141c5  lea     edx, [rbp+3Ch]
0x1800141c8  jmp     loc_180014293
0x1800141cd  call    IsDirectUIUnInitThreadPresent
0x1800141d2  test    al, al
0x1800141d4  jz      short loc_18001422E
0x1800141d6  mov     ecx, 10002h
0x1800141db  call    cs:__imp_DirectUIInitThread
0x1800141e1  test    eax, eax
0x1800141e3  jns     short loc_180014220
0x1800141e5  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800141ec  lea     this, WPP_GLOBAL_Control
0x1800141f3  cmp     r10, this
0x1800141f6  jz      loc_1800142B9
0x1800141fc  test    byte ptr [r10+44h], 8
0x180014201  jz      loc_1800142B9
0x180014207  cmp     byte ptr [r10+41h], 2
0x18001420c  jb      loc_1800142B9
0x180014212  mov     this, [r10+38h]
0x180014216  mov     edx, 3Eh ; '>'
0x18001421b  mov     r9d, eax
0x18001421e  jmp     short loc_18001425C
0x180014220  mov     edx, edi; fInProcActivation
0x180014222  mov     this, rsi; pUIContext
0x180014225  call    _ActivateAppContainerWorker
0x18001422a  mov     ebp, eax
0x18001422c  jmp     short loc_1800142A6
0x18001422e  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014235  lea     this, WPP_GLOBAL_Control
0x18001423c  cmp     rax, this
0x18001423f  jz      short loc_1800142B9
0x180014241  test    byte ptr [rax+44h], 8
0x180014245  jz      short loc_1800142B9
0x180014247  cmp     byte ptr [rax+41h], 2
0x18001424b  jb      short loc_1800142B9
0x18001424d  mov     this, [rax+38h]; Logger
0x180014251  mov     edx, 3Dh ; '='; id
0x180014256  mov     r9d, 80004001h; _a1
0x18001425c  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180014263  call    WPP_SF_d
0x180014268  jmp     short loc_1800142B9
0x18001426a  mov     ebx, 80004001h
0x18001426f  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180014276  lea     this, WPP_GLOBAL_Control
0x18001427d  cmp     rax, this
0x180014280  jz      short loc_1800142A6
0x180014282  test    byte ptr [rax+44h], 8
0x180014286  jz      short loc_1800142A6
0x180014288  cmp     byte ptr [rax+41h], 2
0x18001428c  jb      short loc_1800142A6
0x18001428e  mov     edx, 3Bh ; ';'; id
0x180014293  mov     this, [rax+38h]; Logger
0x180014297  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x18001429e  mov     r9d, ebx; _a1
0x1800142a1  call    WPP_SF_d
0x1800142a6  call    IsDirectUIUnInitThreadPresent
0x1800142ab  test    al, al
0x1800142ad  jz      short loc_1800142B5
0x1800142af  call    cs:__imp_DirectUIUnInitThread
0x1800142b5  test    ebx, ebx
0x1800142b7  js      short loc_1800142C8
0x1800142b9  call    IsDirectUIUnInitThreadPresent
0x1800142be  test    al, al
0x1800142c0  jz      short loc_1800142C8
0x1800142c2  call    cs:__imp_DirectUIUnInitProc
0x1800142c8  mov     eax, ebp
0x1800142ca  add     rsp, 28h
0x1800142ce  pop     rdi
0x1800142cf  pop     rsi
0x1800142d0  pop     rbp
0x1800142d1  pop     rbx
0x1800142d2  retn
```
