# COleControl::OnChar(uint,uint,uint)

- ea: `0x1800b9000`
- end: `0x1800b925d`
- name: `?OnChar@COleControl@@IEAAXIII@Z`
- size: `605`
- prototype: `void __fastcall(COleControl *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180025280`
- `0x1800b8a50`
- `0x1800b9000`
- `0x1800b95cc`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b903b`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b9106`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b903b`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b9106`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b91c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b91ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9213`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b91c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b91ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b9213`
- `USER32!PeekMessageW` at `0x1800b9083`
- `USER32!PeekMessageW` at `0x1800b912e`
- `USER32!PeekMessageW` at `0x1800b9136`
- `USER32!PeekMessageW` at `0x1800b9237`
- `USER32!PeekMessageW` at `0x1800b9083`
- `USER32!PeekMessageW` at `0x1800b912e`
- `USER32!PeekMessageW` at `0x1800b9136`
- `USER32!PeekMessageW` at `0x1800b9237`
- `USER32!GetClassNameW` at `0x1800b9195`
- `USER32!GetClassNameW` at `0x1800b9195`

## string_xrefs

- `0x1800b91f7`: `ComboBox`

## pseudocode

```c
void __fastcall COleControl::OnChar(HWND *this, unsigned int a2, unsigned __int16 a3, unsigned __int16 a4)
{
  unsigned int v7; // esi
  __int16 v8; // di
  BOOL v9; // r14d
  HWND v10; // r15
  unsigned __int16 v11; // cx
  BOOL v12; // eax
  HWND v13; // rdx
  unsigned __int8 v14[2]; // [rsp+30h] [rbp-49h] BYREF
  struct tagMSG Msg; // [rsp+38h] [rbp-41h] BYREF
  WCHAR ClassName[12]; // [rsp+68h] [rbp-11h] BYREF

  *(_WORD *)v14 = a2;
  v7 = a2;
  v8 = a2;
  memset(&Msg, 0, sizeof(Msg));
  v9 = IsDBCSLeadByte(a2);
  if ( (COleControl::GetStockEventMask((COleControl *)this) & 8) == 0 )
  {
    v11 = *(_WORD *)v14;
    goto LABEL_11;
  }
  if ( v9 && PeekMessageW(&Msg, this[8], 0x102u, 0x102u, 2u) )
  {
    v8 = LOWORD(Msg.wParam) | (*(_WORD *)v14 << 8);
    *(_WORD *)v14 = v8;
  }
  else
  {
    v8 = *(_WORD *)v14;
  }
  v10 = this[8];
  COleControl::FireEvent((COleControl *)this, -603, "B", v14);
  v11 = *(_WORD *)v14;
  if ( *(_WORD *)v14 )
  {
    (*((void (__fastcall **)(HWND *, _QWORD))*this + 64))(this, *(unsigned __int16 *)v14);
    v11 = *(_WORD *)v14;
  }
  if ( this[8] == v10 )
  {
LABEL_11:
    if ( !v11 )
    {
LABEL_20:
      if ( v9
        && (!GetClassNameW(this[8], ClassName, 10)
         || CompareStringW(0x7Fu, 1u, ClassName, -1, L"Edit", -1) != 2
         && CompareStringW(0x7Fu, 1u, ClassName, -1, L"ListBox", -1) != 2
         && CompareStringW(0x7Fu, 1u, ClassName, -1, L"ComboBox", -1) != 2) )
      {
        PeekMessageW(&Msg, this[8], 0x102u, 0x102u, 3u);
      }
      return;
    }
    if ( v8 != v11 )
    {
      v7 = v11;
      v12 = IsDBCSLeadByte(HIBYTE(v11));
      if ( v9 )
      {
        v13 = this[8];
        if ( v12 )
        {
          PeekMessageW(&Msg, v13, 0x102u, 0x102u, 3u);
LABEL_18:
          _AfxPostTrailByte((struct CWnd *)this, v14[0]);
          v7 = v14[1];
          goto LABEL_19;
        }
        PeekMessageW(&Msg, v13, 0x102u, 0x102u, 3u);
      }
      else if ( v12 )
      {
        goto LABEL_18;
      }
    }
LABEL_19:
    (*((void (__fastcall **)(HWND *, __int64, _QWORD, _QWORD))*this + 42))(this, 258, v7, a3 | (a4 << 16));
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x1800b9000  push    rbp
0x1800b9002  push    rbx
0x1800b9003  push    rsi
0x1800b9004  push    rdi
0x1800b9005  push    r12
0x1800b9007  push    r13
0x1800b9009  push    r14
0x1800b900b  push    r15
0x1800b900d  lea     rbp, [rsp-1Fh]
0x1800b9012  sub     rsp, 98h
0x1800b9019  mov     rax, cs:__security_cookie
0x1800b9020  xor     rax, rsp
0x1800b9023  mov     [rbp+57h+var_50], rax
0x1800b9027  mov     rbx, rcx
0x1800b902a  mov     word ptr [rbp+57h+var_A0], dx
0x1800b902e  mov     cl, dl; TestChar
0x1800b9030  mov     r13d, r9d
0x1800b9033  mov     r12d, r8d
0x1800b9036  mov     esi, edx
0x1800b9038  movzx   edi, dx
0x1800b903b  call    cs:__imp_IsDBCSLeadByte
0x1800b9041  xorps   xmm0, xmm0
0x1800b9044  mov     rcx, rbx; this
0x1800b9047  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800b904b  mov     r14d, eax
0x1800b904e  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800b9052  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800b9056  call    ?GetStockEventMask@COleControl@@IEBAKXZ; COleControl::GetStockEventMask(void)
0x1800b905b  mov     ecx, 102h
0x1800b9060  test    al, 8
0x1800b9062  jz      loc_1800B90ED
0x1800b9068  test    r14d, r14d
0x1800b906b  jz      short loc_1800B909F
0x1800b906d  mov     rdx, [rbx+40h]; hWnd
0x1800b9071  mov     r9d, ecx; wMsgFilterMax
0x1800b9074  mov     r8d, ecx; wMsgFilterMin
0x1800b9077  mov     [rsp+0D0h+wRemoveMsg], 2; wRemoveMsg
0x1800b907f  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800b9083  call    cs:__imp_PeekMessageW
0x1800b9089  test    eax, eax
0x1800b908b  jz      short loc_1800B909F
0x1800b908d  movzx   edi, word ptr [rbp+57h+var_A0]
0x1800b9091  shl     di, 8
0x1800b9095  or      di, word ptr [rbp+57h+Msg.wParam]
0x1800b9099  mov     word ptr [rbp+57h+var_A0], di
0x1800b909d  jmp     short loc_1800B90A3
0x1800b909f  movzx   edi, word ptr [rbp+57h+var_A0]
0x1800b90a3  mov     r15, [rbx+40h]
0x1800b90a7  lea     r9, [rbp+57h+var_A0]
0x1800b90ab  lea     r8, aB; "B"
0x1800b90b2  mov     edx, 0FFFFFDA5h; int
0x1800b90b7  mov     rcx, rbx; this
0x1800b90ba  call    ?FireEvent@COleControl@@QEAAXJPEAEZZ; COleControl::FireEvent(long,uchar *,...)
0x1800b90bf  movzx   ecx, word ptr [rbp+57h+var_A0]
0x1800b90c3  test    cx, cx
0x1800b90c6  jz      short loc_1800B90E1
0x1800b90c8  mov     rax, [rbx]
0x1800b90cb  movzx   edx, cx
0x1800b90ce  mov     rcx, rbx
0x1800b90d1  mov     rax, [rax+200h]
0x1800b90d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b90dd  movzx   ecx, word ptr [rbp+57h+var_A0]
0x1800b90e1  cmp     [rbx+40h], r15
0x1800b90e5  jnz     loc_1800B923D
0x1800b90eb  jmp     short loc_1800B90F1
0x1800b90ed  movzx   ecx, word ptr [rbp+57h+var_A0]
0x1800b90f1  test    cx, cx
0x1800b90f4  jz      loc_1800B917E
0x1800b90fa  cmp     di, cx
0x1800b90fd  jz      short loc_1800B9154
0x1800b90ff  movzx   esi, cx
0x1800b9102  shr     cx, 8; TestChar
0x1800b9106  call    cs:__imp_IsDBCSLeadByte
0x1800b910c  test    r14d, r14d
0x1800b910f  jz      short loc_1800B913E
0x1800b9111  mov     rdx, [rbx+40h]; hWnd
0x1800b9115  mov     r9d, 102h; wMsgFilterMax
0x1800b911b  mov     [rsp+0D0h+wRemoveMsg], 3; wRemoveMsg
0x1800b9123  mov     r8d, r9d; wMsgFilterMin
0x1800b9126  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800b912a  test    eax, eax
0x1800b912c  jz      short loc_1800B9136
0x1800b912e  call    cs:__imp_PeekMessageW
0x1800b9134  jmp     short loc_1800B9142
0x1800b9136  call    cs:__imp_PeekMessageW
0x1800b913c  jmp     short loc_1800B9154
0x1800b913e  test    eax, eax
0x1800b9140  jz      short loc_1800B9154
0x1800b9142  mov     dl, [rbp+57h+var_A0]; unsigned __int8
0x1800b9145  mov     rcx, rbx; struct CWnd *
0x1800b9148  call    ?_AfxPostTrailByte@@YAXPEAVCWnd@@E@Z; _AfxPostTrailByte(CWnd *,uchar)
0x1800b914d  movzx   esi, word ptr [rbp+57h+var_A0]
0x1800b9151  shr     esi, 8
0x1800b9154  mov     r10, [rbx]
0x1800b9157  mov     edx, 102h
0x1800b915c  movzx   ecx, r13w
0x1800b9160  shl     ecx, 10h
0x1800b9163  movzx   eax, r12w
0x1800b9167  or      ecx, eax
0x1800b9169  mov     r8d, esi
0x1800b916c  mov     rax, [r10+150h]
0x1800b9173  movsxd  r9, ecx
0x1800b9176  mov     rcx, rbx
0x1800b9179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b917e  test    r14d, r14d
0x1800b9181  jz      loc_1800B923D
0x1800b9187  mov     rcx, [rbx+40h]; hWnd
0x1800b918b  lea     rdx, [rbp+57h+ClassName]; lpClassName
0x1800b918f  mov     r8d, 0Ah; nMaxCount
0x1800b9195  call    cs:__imp_GetClassNameW
0x1800b919b  test    eax, eax
0x1800b919d  jz      short loc_1800B921E
0x1800b919f  or      edi, 0FFFFFFFFh
0x1800b91a2  lea     rax, aEdit_0; "Edit"
0x1800b91a9  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1800b91ad  lea     r8, [rbp+57h+ClassName]; lpString1
0x1800b91b1  mov     r9d, edi; cchCount1
0x1800b91b4  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1800b91b9  lea     esi, [rdi+2]
0x1800b91bc  lea     r14d, [rsi+7Eh]
0x1800b91c0  mov     edx, esi; dwCmpFlags
0x1800b91c2  mov     ecx, r14d; Locale
0x1800b91c5  call    cs:__imp_CompareStringW
0x1800b91cb  cmp     eax, 2
0x1800b91ce  jz      short loc_1800B923D
0x1800b91d0  lea     rax, aListbox_0; "ListBox"
0x1800b91d7  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1800b91db  mov     r9d, edi; cchCount1
0x1800b91de  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1800b91e3  lea     r8, [rbp+57h+ClassName]; lpString1
0x1800b91e7  mov     edx, esi; dwCmpFlags
0x1800b91e9  mov     ecx, r14d; Locale
0x1800b91ec  call    cs:__imp_CompareStringW
0x1800b91f2  cmp     eax, 2
0x1800b91f5  jz      short loc_1800B923D
0x1800b91f7  lea     rax, aCombobox; "ComboBox"
0x1800b91fe  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1800b9202  mov     r9d, edi; cchCount1
0x1800b9205  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1800b920a  lea     r8, [rbp+57h+ClassName]; lpString1
0x1800b920e  mov     edx, esi; dwCmpFlags
0x1800b9210  mov     ecx, r14d; Locale
0x1800b9213  call    cs:__imp_CompareStringW
0x1800b9219  cmp     eax, 2
0x1800b921c  jz      short loc_1800B923D
0x1800b921e  mov     rdx, [rbx+40h]; hWnd
0x1800b9222  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800b9226  mov     r9d, 102h; wMsgFilterMax
0x1800b922c  mov     [rsp+0D0h+wRemoveMsg], 3; wRemoveMsg
0x1800b9234  mov     r8d, r9d; wMsgFilterMin
0x1800b9237  call    cs:__imp_PeekMessageW
0x1800b923d  mov     rcx, [rbp+57h+var_50]
0x1800b9241  xor     rcx, rsp; StackCookie
0x1800b9244  call    __security_check_cookie
0x1800b9249  add     rsp, 98h
0x1800b9250  pop     r15
0x1800b9252  pop     r14
0x1800b9254  pop     r13
0x1800b9256  pop     r12
0x1800b9258  pop     rdi
0x1800b9259  pop     rsi
0x1800b925a  pop     rbx
0x1800b925b  pop     rbp
0x1800b925c  retn
```
