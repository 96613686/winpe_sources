# WdagPluginEvaluate

- ea: `0x14002dbbc`
- end: `0x14002dda0`
- name: `WdagPluginEvaluate`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002daa0`

## callees

- `0x140001010`
- `0x140001044`
- `0x140006a20`
- `0x14002023c`
- `0x14002dbbc`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x14002dca3`
- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x14002dca3`

## pseudocode

```c
__int64 __fastcall WdagPluginEvaluate(__int64 a1, __int64 a2)
{
  int v2; // ebx
  bool v3; // r14
  unsigned int v5; // edi
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int8 *v10; // rdx
  ULONG v12; // [rsp+20h] [rbp-99h]
  char v13[4]; // [rsp+40h] [rbp-79h] BYREF
  int v14; // [rsp+44h] [rbp-75h] BYREF
  __int64 v15; // [rsp+48h] [rbp-71h] BYREF
  int v16; // [rsp+50h] [rbp-69h] BYREF
  __int128 v17; // [rsp+58h] [rbp-61h] BYREF
  __int64 v18; // [rsp+68h] [rbp-51h] BYREF
  __int128 v19; // [rsp+70h] [rbp-49h] BYREF
  int v20; // [rsp+80h] [rbp-39h]
  int v21; // [rsp+88h] [rbp-31h]
  __int64 *v22; // [rsp+90h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+A0h] [rbp-19h] BYREF
  int *v24; // [rsp+C0h] [rbp+7h]
  __int64 v25; // [rsp+C8h] [rbp+Fh]
  __int64 *v26; // [rsp+D0h] [rbp+17h]
  __int64 v27; // [rsp+D8h] [rbp+1Fh]

  v2 = 0;
  v15 = 0;
  v13[0] = 0;
  v3 = dword_140019000 != 0;
  v5 = 0;
  v16 = 4;
  v17 = 0;
  v18 = 1;
  if ( *(_DWORD *)(a1 + 16) )
  {
    while ( 1 )
    {
      v2 = AiEvaluateAppLockerPolicyClass(a1, a2, *(_QWORD *)(a1 + 24) + 32LL * v5, *(void **)a1, (__int64)&v15);
      if ( v2 < 0 )
        break;
      if ( (int)v15 >= 0 )
      {
        v6 = *(void **)a1;
        *((_QWORD *)&v17 + 1) = &v19;
        *(_QWORD *)&v17 = 0x100000001LL;
        v22 = &v18;
        v20 = 6;
        v19 = *(_OWORD *)L":<";
        v21 = 1;
        v2 = SeSetSecurityAttributesTokenEx(v6, 0, 0, 0, &v16, &v17, v13);
        if ( v2 < 0 )
        {
          if ( v3 && (unsigned int)dword_140019000 > 4 && tlgKeywordOn(a1, 0x400000000000LL) )
          {
            v24 = &v14;
            v10 = (unsigned __int8 *)&word_140016176;
            v12 = 3;
LABEL_15:
            v14 = v2;
            v25 = 4;
            tlgWriteTransfer_EtwWriteTransfer(v7, v10, v8, v9, v12, &v23);
            return (unsigned int)v2;
          }
          return (unsigned int)v2;
        }
      }
      if ( ++v5 >= *(_DWORD *)(a1 + 16) )
        return (unsigned int)v2;
    }
    if ( v3 && (unsigned int)dword_140019000 > 4 && tlgKeywordOn(a1, 0x400000000000LL) )
    {
      v27 = 4;
      v24 = &v14;
      v10 = (unsigned __int8 *)&dword_1400161CC;
      v26 = &v15;
      v12 = 4;
      goto LABEL_15;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002dbbc  mov     [rsp-8+arg_8], rbx
0x14002dbc1  mov     [rsp-8+arg_10], rsi
0x14002dbc6  push    rbp
0x14002dbc7  push    rdi
0x14002dbc8  push    r12
0x14002dbca  push    r13
0x14002dbcc  push    r14
0x14002dbce  lea     rbp, [rsp-37h]
0x14002dbd3  sub     rsp, 0F0h
0x14002dbda  mov     rax, cs:__security_cookie
0x14002dbe1  xor     rax, rsp
0x14002dbe4  mov     [rbp+57h+var_30], rax
0x14002dbe8  mov     eax, cs:dword_140019000
0x14002dbee  xor     ebx, ebx
0x14002dbf0  test    eax, eax
0x14002dbf2  mov     [rbp+57h+var_C8], rbx
0x14002dbf6  xorps   xmm0, xmm0
0x14002dbf9  mov     [rbp+57h+var_D0], bl
0x14002dbfc  setnz   r14b
0x14002dc00  mov     rsi, rcx
0x14002dc03  xor     edi, edi
0x14002dc05  lea     r12d, [rbx+4]
0x14002dc09  lea     r13d, [rbx+1]
0x14002dc0d  mov     [rbp+57h+var_C0], r12d
0x14002dc11  movups  [rbp+57h+var_B8], xmm0
0x14002dc15  mov     [rbp+57h+var_A8], r13
0x14002dc19  cmp     [rcx+10h], ebx
0x14002dc1c  jbe     loc_14002DD75
0x14002dc22  mov     r9, [rsi]
0x14002dc25  lea     rax, [rbp+57h+var_C8]
0x14002dc29  mov     r8d, edi
0x14002dc2c  shl     r8, 5
0x14002dc30  add     r8, [rsi+18h]
0x14002dc34  mov     qword ptr [rsp+110h+var_F0], rax
0x14002dc39  call    AiEvaluateAppLockerPolicyClass
0x14002dc3e  mov     ebx, eax
0x14002dc40  test    eax, eax
0x14002dc42  js      loc_14002DD17
0x14002dc48  cmp     dword ptr [rbp+57h+var_C8], 0
0x14002dc4c  jl      short loc_14002DCB5
0x14002dc4e  movups  xmm0, xmmword ptr cs:asc_140009ED0; ":<"
0x14002dc55  mov     rcx, [rsi]
0x14002dc58  lea     rax, [rbp+57h+var_A0]
0x14002dc5c  mov     qword ptr [rbp+57h+var_B8+8], rax
0x14002dc60  xor     r9d, r9d
0x14002dc63  lea     rax, [rbp+57h+var_A8]
0x14002dc67  mov     dword ptr [rbp+57h+var_B8], r13d
0x14002dc6b  mov     [rbp+57h+var_80], rax
0x14002dc6f  xor     r8d, r8d
0x14002dc72  lea     rax, [rbp+57h+var_D0]
0x14002dc76  mov     dword ptr [rbp+57h+var_B8+4], r13d
0x14002dc7a  mov     [rsp+110h+var_E0], rax
0x14002dc7f  xor     edx, edx
0x14002dc81  lea     rax, [rbp+57h+var_B8]
0x14002dc85  mov     [rbp+57h+var_90], 6
0x14002dc8c  mov     [rsp+110h+var_E8], rax
0x14002dc91  lea     rax, [rbp+57h+var_C0]
0x14002dc95  mov     qword ptr [rsp+110h+var_F0], rax
0x14002dc9a  movdqu  [rbp+57h+var_A0], xmm0
0x14002dc9f  mov     [rbp+57h+var_88], r13d
0x14002dca3  call    cs:__imp_SeSetSecurityAttributesTokenEx
0x14002dcaa  nop     dword ptr [rax+rax+00h]
0x14002dcaf  mov     ebx, eax
0x14002dcb1  test    eax, eax
0x14002dcb3  js      short loc_14002DCC6
0x14002dcb5  add     edi, r13d
0x14002dcb8  cmp     edi, [rsi+10h]
0x14002dcbb  jb      loc_14002DC22
0x14002dcc1  jmp     loc_14002DD75
0x14002dcc6  test    r14b, r14b
0x14002dcc9  jz      loc_14002DD75
0x14002dccf  mov     eax, cs:dword_140019000
0x14002dcd5  cmp     eax, r12d
0x14002dcd8  jbe     loc_14002DD75
0x14002dcde  mov     rdx, 400000000000h
0x14002dce8  call    _tlgKeywordOn
0x14002dced  test    al, al
0x14002dcef  jz      loc_14002DD75
0x14002dcf5  lea     rax, [rbp+57h+var_CC]
0x14002dcf9  mov     [rbp+57h+var_50], rax
0x14002dcfd  lea     rdx, word_140016176
0x14002dd04  lea     rax, [rbp+57h+var_70]
0x14002dd08  mov     [rsp+110h+var_E8], rax
0x14002dd0d  mov     [rsp+110h+var_F0], 3
0x14002dd15  jmp     short loc_14002DD69
0x14002dd17  test    r14b, r14b
0x14002dd1a  jz      short loc_14002DD75
0x14002dd1c  mov     eax, cs:dword_140019000
0x14002dd22  cmp     eax, r12d
0x14002dd25  jbe     short loc_14002DD75
0x14002dd27  mov     rdx, 400000000000h
0x14002dd31  call    _tlgKeywordOn
0x14002dd36  test    al, al
0x14002dd38  jz      short loc_14002DD75
0x14002dd3a  lea     rax, [rbp+57h+var_CC]
0x14002dd3e  mov     [rbp+57h+var_38], r12
0x14002dd42  mov     [rbp+57h+var_50], rax
0x14002dd46  lea     rdx, dword_1400161CC; int
0x14002dd4d  mov     eax, dword ptr [rbp+57h+var_C8]
0x14002dd50  mov     dword ptr [rbp+57h+var_C8], eax
0x14002dd53  lea     rax, [rbp+57h+var_C8]
0x14002dd57  mov     [rbp+57h+var_40], rax
0x14002dd5b  lea     rax, [rbp+57h+var_70]
0x14002dd5f  mov     [rsp+110h+var_E8], rax; __int64
0x14002dd64  mov     [rsp+110h+var_F0], r12d; ULONG
0x14002dd69  mov     [rbp+57h+var_CC], ebx
0x14002dd6c  mov     [rbp+57h+var_48], r12
0x14002dd70  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002dd75  mov     eax, ebx
0x14002dd77  mov     rcx, [rbp+57h+var_30]
0x14002dd7b  xor     rcx, rsp; StackCookie
0x14002dd7e  call    __security_check_cookie
0x14002dd83  lea     r11, [rsp+110h+var_20]
0x14002dd8b  mov     rbx, [r11+38h]
0x14002dd8f  mov     rsi, [r11+40h]
0x14002dd93  mov     rsp, r11
0x14002dd96  pop     r14
0x14002dd98  pop     r13
0x14002dd9a  pop     r12
0x14002dd9c  pop     rdi
0x14002dd9d  pop     rbp
0x14002dd9e  retn
```
