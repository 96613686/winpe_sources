# sub_409AEE

- ea: `0x409aee`
- end: `0x409d0a`
- name: `sub_409AEE`
- size: `540`
- prototype: `_DWORD *__thiscall(_DWORD *this, _DWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x4018e5`

## callees

- `0x4015d2`
- `0x4015fb`
- `0x401cac`
- `0x401cfa`
- `0x401d46`
- `0x401fbb`
- `0x405b8c`
- `0x409aee`
- `0x409d8e`
- `0x409dbf`
- `0x409ef8`
- `0x409feb`
- `0x40a0cf`
- `0x40a121`
- `0x40a243`
- `0x40a31b`
- `0x40a3a1`

## string_xrefs

- `0x409c75`: `/broker`
- `0x409c8d`: `uninstall`

## pseudocode

```c
_DWORD *__thiscall sub_409AEE(_DWORD *this, _DWORD *a2)
{
  int v3; // eax
  int *v4; // eax
  int v5; // ecx
  int v6; // ecx
  int v7; // eax
  int v9; // [esp+8h] [ebp-8h] BYREF
  int v10; // [esp+Ch] [ebp-4h] BYREF

  *a2 = 0;
  v3 = sub_4015FB();
  sub_401FBB(v3);
  switch ( *this )
  {
    case 1:
      sub_401D46(a2);
      return a2;
    case 2:
      sub_401CFA((wchar_t *)aC);
      sub_409D8E(&v10, &v9);
      sub_4015D2(v9 - 16);
      goto LABEL_7;
    case 3:
      sub_401CFA((wchar_t *)L"svc");
      goto LABEL_9;
    case 4:
      sub_401CFA(L"regserver");
      goto LABEL_9;
    case 5:
      sub_401CFA(L"unregserver");
      goto LABEL_9;
    case 7:
      v9 = 0;
      sub_401CFA(L"crash");
      goto LABEL_9;
    case 8:
      v4 = (int *)sub_409DBF(&v10);
      goto LABEL_4;
    case 9:
      v4 = (int *)sub_409FEB(&v10);
      goto LABEL_4;
    case 0xA:
      v4 = (int *)sub_40A0CF(&v10);
      goto LABEL_4;
    case 0xC:
      v4 = (int *)sub_40A121(&v10);
      goto LABEL_4;
    case 0xE:
      v4 = (int *)sub_40A243(&v10);
      goto LABEL_4;
    case 0xF:
      v4 = (int *)sub_40A31B(&v10);
      goto LABEL_4;
    case 0x11:
      sub_401CFA(L"cr");
      goto LABEL_9;
    case 0x12:
      sub_401CFA((wchar_t *)L"-Embedding");
      goto LABEL_7;
    case 0x15:
      sub_409EF8(&v10, L"registerproduct");
      goto LABEL_7;
    case 0x16:
      sub_409EF8(&v10, L"unregisterproduct");
      goto LABEL_7;
    case 0x17:
      sub_401CFA(L"regsvc");
      goto LABEL_9;
    case 0x18:
      sub_401CFA(L"unregsvc");
      goto LABEL_9;
    case 0x19:
      sub_401CFA(L"crashhandler");
      goto LABEL_9;
    case 0x1A:
      sub_401CFA(L"/broker");
      goto LABEL_7;
    case 0x1B:
      sub_401CFA(L"/ondemand");
LABEL_7:
      v4 = &v10;
      goto LABEL_4;
    case 0x1C:
      sub_401CFA(L"medsvc");
      goto LABEL_9;
    case 0x1D:
      sub_401CFA(L"uninstall");
LABEL_9:
      sub_409D8E(&v9, &v10);
      sub_4015D2(v10 - 16);
      goto LABEL_10;
    case 0x1E:
      v9 = 0;
      v7 = sub_4015FB();
      sub_401FBB(v7);
      sub_405B8C(&v9, L"/%s %s", L"ping", this[9]);
LABEL_10:
      sub_401CAC(&v9);
      v5 = v9;
      goto LABEL_5;
    case 0x1F:
      sub_401CFA((wchar_t *)L"healthcheck");
      sub_409D8E(&v9, &v10);
      sub_4015D2(v10 - 16);
      sub_401CAC(&v9);
      v6 = v9 - 16;
      goto LABEL_35;
    case 0x21:
      v4 = (int *)sub_40A3A1(&v10);
LABEL_4:
      sub_401CAC(v4);
      v5 = v10;
LABEL_5:
      v6 = v5 - 16;
LABEL_35:
      sub_4015D2(v6);
      break;
    default:
      return a2;
  }
  return a2;
}

```

## disassembly

```asm
0x409aee  push    ebp
0x409aef  mov     ebp, esp
0x409af1  push    ecx
0x409af2  push    ecx
0x409af3  push    esi
0x409af4  mov     esi, [ebp+arg_0]
0x409af7  push    edi
0x409af8  mov     edi, ecx
0x409afa  and     dword ptr [esi], 0
0x409afd  call    sub_4015FB
0x409b02  push    eax
0x409b03  mov     ecx, esi
0x409b05  call    sub_401FBB
0x409b0a  mov     eax, [edi]
0x409b0c  dec     eax; switch 33 cases
0x409b0d  cmp     eax, 20h
0x409b10  ja      def_409B16; jumptable 00409B16 default case, cases 6,11,13,16,19,20,32
0x409b16  jmp     ds:jpt_409B16[eax*4]; switch jump
0x409b1d  mov     ecx, esi; jumptable 00409B16 case 1
0x409b1f  call    sub_401D46
0x409b24  jmp     def_409B16; jumptable 00409B16 default case, cases 6,11,13,16,19,20,32
0x409b29  lea     eax, [ebp+var_4]; jumptable 00409B16 case 33
0x409b2c  mov     ecx, edi
0x409b2e  push    eax
0x409b2f  call    sub_40A3A1
0x409b34  push    eax
0x409b35  mov     ecx, esi
0x409b37  call    sub_401CAC
0x409b3c  mov     ecx, [ebp+var_4]
0x409b3f  lea     ecx, [ecx-10h]
0x409b42  jmp     loc_409CFD
0x409b47  push    offset aC; jumptable 00409B16 case 2
0x409b4c  lea     ecx, [ebp+var_8]
0x409b4f  call    sub_401CFA
0x409b54  lea     eax, [ebp+var_8]
0x409b57  push    eax
0x409b58  lea     eax, [ebp+var_4]
0x409b5b  push    eax
0x409b5c  call    sub_409D8E
0x409b61  mov     ecx, [ebp+var_8]
0x409b64  lea     ecx, [ecx-10h]
0x409b67  call    sub_4015D2
0x409b6c  lea     eax, [ebp+var_4]
0x409b6f  jmp     short loc_409B34
0x409b71  push    offset aSvc; jumptable 00409B16 case 3
0x409b76  lea     ecx, [ebp+var_4]
0x409b79  call    sub_401CFA
0x409b7e  lea     eax, [ebp+var_4]
0x409b81  push    eax
0x409b82  lea     eax, [ebp+var_8]
0x409b85  push    eax
0x409b86  call    sub_409D8E
0x409b8b  mov     ecx, [ebp+var_4]
0x409b8e  lea     ecx, [ecx-10h]
0x409b91  call    sub_4015D2
0x409b96  lea     eax, [ebp+var_8]
0x409b99  mov     ecx, esi
0x409b9b  push    eax
0x409b9c  call    sub_401CAC
0x409ba1  mov     ecx, [ebp+var_8]
0x409ba4  jmp     short loc_409B3F
0x409ba6  push    offset aRegserver; jumptable 00409B16 case 4
0x409bab  jmp     short loc_409B76
0x409bad  push    offset aUnregserver; jumptable 00409B16 case 5
0x409bb2  jmp     short loc_409B76
0x409bb4  and     [ebp+var_8], 0; jumptable 00409B16 case 7
0x409bb8  push    offset aCrash; "crash"
0x409bbd  jmp     short loc_409B76
0x409bbf  lea     eax, [ebp+var_4]; jumptable 00409B16 case 8
0x409bc2  mov     ecx, edi
0x409bc4  push    eax
0x409bc5  call    sub_409DBF
0x409bca  jmp     loc_409B34
0x409bcf  lea     eax, [ebp+var_4]; jumptable 00409B16 case 9
0x409bd2  mov     ecx, edi
0x409bd4  push    eax
0x409bd5  call    sub_409FEB
0x409bda  jmp     loc_409B34
0x409bdf  lea     eax, [ebp+var_4]; jumptable 00409B16 case 10
0x409be2  mov     ecx, edi
0x409be4  push    eax
0x409be5  call    sub_40A0CF
0x409bea  jmp     loc_409B34
0x409bef  lea     eax, [ebp+var_4]; jumptable 00409B16 case 12
0x409bf2  mov     ecx, edi
0x409bf4  push    eax
0x409bf5  call    sub_40A121
0x409bfa  jmp     loc_409B34
0x409bff  lea     eax, [ebp+var_4]; jumptable 00409B16 case 14
0x409c02  mov     ecx, edi
0x409c04  push    eax
0x409c05  call    sub_40A243
0x409c0a  jmp     loc_409B34
0x409c0f  lea     eax, [ebp+var_4]; jumptable 00409B16 case 15
0x409c12  mov     ecx, edi
0x409c14  push    eax
0x409c15  call    sub_40A31B
0x409c1a  jmp     loc_409B34
0x409c1f  push    offset aCr; jumptable 00409B16 case 17
0x409c24  jmp     loc_409B76
0x409c29  push    offset aEmbedding; jumptable 00409B16 case 18
0x409c2e  lea     ecx, [ebp+var_4]
0x409c31  call    sub_401CFA
0x409c36  jmp     loc_409B6C
0x409c3b  push    offset aRegisterproduc; jumptable 00409B16 case 21
0x409c40  lea     eax, [ebp+var_4]
0x409c43  mov     ecx, edi
0x409c45  push    eax
0x409c46  call    sub_409EF8
0x409c4b  jmp     loc_409B6C
0x409c50  push    offset aUnregisterprod; jumptable 00409B16 case 22
0x409c55  jmp     short loc_409C40
0x409c57  push    offset aRegsvc; jumptable 00409B16 case 23
0x409c5c  jmp     loc_409B76
0x409c61  push    offset aUnregsvc; jumptable 00409B16 case 24
0x409c66  jmp     loc_409B76
0x409c6b  push    offset aCrashhandler; jumptable 00409B16 case 25
0x409c70  jmp     loc_409B76
0x409c75  push    offset aBroker; jumptable 00409B16 case 26
0x409c7a  jmp     short loc_409C2E
0x409c7c  push    offset aOndemand; jumptable 00409B16 case 27
0x409c81  jmp     short loc_409C2E
0x409c83  push    offset aMedsvc; jumptable 00409B16 case 28
0x409c88  jmp     loc_409B76
0x409c8d  push    offset aUninstall; jumptable 00409B16 case 29
0x409c92  jmp     loc_409B76
0x409c97  and     [ebp+var_8], 0; jumptable 00409B16 case 30
0x409c9b  call    sub_4015FB
0x409ca0  push    eax
0x409ca1  lea     ecx, [ebp+var_8]
0x409ca4  call    sub_401FBB
0x409ca9  push    dword ptr [edi+24h]
0x409cac  lea     eax, [ebp+var_8]
0x409caf  push    offset aPing; "ping"
0x409cb4  push    offset aSS_0; "/%s %s"
0x409cb9  push    eax
0x409cba  call    sub_405B8C
0x409cbf  add     esp, 10h
0x409cc2  jmp     loc_409B96
0x409cc7  push    offset aHealthcheck; jumptable 00409B16 case 31
0x409ccc  lea     ecx, [ebp+var_4]
0x409ccf  call    sub_401CFA
0x409cd4  lea     eax, [ebp+var_4]
0x409cd7  push    eax
0x409cd8  lea     eax, [ebp+var_8]
0x409cdb  push    eax
0x409cdc  call    sub_409D8E
0x409ce1  mov     ecx, [ebp+var_4]
0x409ce4  lea     ecx, [ecx-10h]
0x409ce7  call    sub_4015D2
0x409cec  lea     eax, [ebp+var_8]
0x409cef  mov     ecx, esi
0x409cf1  push    eax
0x409cf2  call    sub_401CAC
0x409cf7  mov     ecx, [ebp+var_8]
0x409cfa  add     ecx, 0FFFFFFF0h
0x409cfd  call    sub_4015D2
0x409d02  pop     edi; jumptable 00409B16 default case, cases 6,11,13,16,19,20,32
0x409d03  mov     eax, esi
0x409d05  pop     esi
0x409d06  leave
0x409d07  retn    4
```
