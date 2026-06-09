# PrjfSendStartDirectoryEnumerationCommand

- ea: `0x140035060`
- end: `0x140035232`
- name: `PrjfSendStartDirectoryEnumerationCommand`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140025734`
- `0x140039de8`

## callees

- `0x14000be80`
- `0x14000d754`
- `0x140032db4`
- `0x140033bd0`
- `0x140035060`
- `0x14003a5cc`

## pseudocode

```c
__int64 __fastcall PrjfSendStartDirectoryEnumerationCommand(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int128 *a4)
{
  __int128 v8; // xmm0
  int v9; // edx
  int v10; // ebx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  __int64 v15; // [rsp+20h] [rbp-E0h]
  PVOID Entry; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h] BYREF
  int v18; // [rsp+6Ch] [rbp-94h] BYREF
  _OWORD v19[34]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v20; // [rsp+2C8h] [rbp+1C8h] BYREF

  Entry = 0;
  memset(v19, 0, sizeof(v19));
  v8 = *a4;
  v20 = 0;
  v18 = 0;
  v17 = 4;
  v19[0] = v8;
  v10 = PrjfPrepareCommandForFileObject(a2, a3, 1, v19, v15, &Entry, &v20);
  if ( v10 >= 0 )
  {
    v10 = PrjfSendCommand(a1, a2, Entry, 0, (__int64)&v18, &v17);
    if ( v10 < 0
      && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        165,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        208,
        v10,
        (__int64)&a3->FileName);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      164,
      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      191,
      v10,
      (__int64)&a3->FileName);
  }
  if ( Entry )
    PrjfFreeCommandBuffer(Entry, v20);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140035060  mov     [rsp-8+arg_0], rbx
0x140035065  mov     [rsp-8+arg_8], rsi
0x14003506a  push    rbp
0x14003506b  push    r14
0x14003506d  push    r15
0x14003506f  lea     rbp, [rsp-190h]
0x140035077  sub     rsp, 290h
0x14003507e  mov     r15, r8
0x140035081  mov     [rsp+2A0h+Entry], 0
0x14003508a  mov     rsi, rdx
0x14003508d  mov     r14, rcx
0x140035090  xor     edx, edx; Val
0x140035092  lea     rcx, [rsp+2A0h+var_230]; void *
0x140035097  mov     r8d, 220h; Size
0x14003509d  mov     rbx, r9
0x1400350a0  call    memset
0x1400350a5  movaps  xmm0, xmmword ptr [rbx]
0x1400350a8  lea     rax, [rbp+1A0h+arg_18]
0x1400350af  mov     [rsp+2A0h+var_270], rax
0x1400350b4  lea     r9, [rsp+2A0h+var_230]
0x1400350b9  lea     rax, [rsp+2A0h+Entry]
0x1400350be  mov     [rbp+1A0h+arg_18], 0
0x1400350c8  mov     r8d, 1
0x1400350ce  mov     [rsp+2A0h+var_278], rax
0x1400350d3  mov     rdx, r15
0x1400350d6  mov     [rsp+2A0h+var_234], 0
0x1400350de  mov     rcx, rsi
0x1400350e1  mov     [rsp+2A0h+var_238], 4
0x1400350e9  movdqu  [rsp+2A0h+var_230], xmm0
0x1400350ef  call    PrjfPrepareCommandForFileObject
0x1400350f4  mov     ebx, eax
0x1400350f6  test    eax, eax
0x1400350f8  jns     short loc_140035159
0x1400350fa  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140035100  lea     rax, WPP_RECORDER_INITIALIZED
0x140035107  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003510e  setnz   r8b
0x140035112  and     dl, 40h
0x140035115  jnz     short loc_140035120
0x140035117  test    r8b, r8b
0x14003511a  jz      loc_1400351FE
0x140035120  lea     rax, [r15+58h]
0x140035124  mov     [rsp+2A0h+var_248], rax
0x140035129  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140035130  mov     [rsp+2A0h+var_250], ebx
0x140035134  mov     [rsp+2A0h+var_258], 12BFh
0x14003513c  mov     [rsp+2A0h+var_260], rax
0x140035141  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140035148  mov     [rsp+2A0h+var_268], rax
0x14003514d  mov     word ptr [rsp+2A0h+var_270], 0A4h
0x140035154  jmp     loc_1400351DC
0x140035159  mov     r8, [rsp+2A0h+Entry]
0x14003515e  lea     rax, [rsp+2A0h+var_238]
0x140035163  mov     [rsp+2A0h+var_278], rax
0x140035168  xor     r9d, r9d
0x14003516b  lea     rax, [rsp+2A0h+var_234]
0x140035170  mov     rdx, rsi
0x140035173  mov     rcx, r14
0x140035176  mov     [rsp+2A0h+var_280], rax
0x14003517b  call    PrjfSendCommand
0x140035180  mov     ebx, eax
0x140035182  test    eax, eax
0x140035184  jns     short loc_1400351FE
0x140035186  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003518c  lea     rax, WPP_RECORDER_INITIALIZED
0x140035193  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003519a  setnz   r8b
0x14003519e  and     dl, 40h
0x1400351a1  jnz     short loc_1400351A8
0x1400351a3  test    r8b, r8b
0x1400351a6  jz      short loc_1400351FE
0x1400351a8  lea     rax, [r15+58h]
0x1400351ac  mov     [rsp+2A0h+var_248], rax
0x1400351b1  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400351b8  mov     [rsp+2A0h+var_250], ebx
0x1400351bc  mov     [rsp+2A0h+var_258], 12D0h
0x1400351c4  mov     [rsp+2A0h+var_260], rax
0x1400351c9  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400351d0  mov     [rsp+2A0h+var_268], rax
0x1400351d5  mov     word ptr [rsp+2A0h+var_270], 0A5h
0x1400351dc  mov     r9, cs:WPP_GLOBAL_Control
0x1400351e3  mov     ecx, 20Eh
0x1400351e8  mov     dword ptr [rsp+2A0h+var_278], 0Eh
0x1400351f0  mov     byte ptr [rsp+2A0h+var_280], 2
0x1400351f5  mov     r9, [r9+40h]
0x1400351f9  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400351fe  cmp     [rsp+2A0h+Entry], 0
0x140035204  jz      short loc_140035216
0x140035206  mov     edx, [rbp+1A0h+arg_18]
0x14003520c  mov     rcx, [rsp+2A0h+Entry]; Entry
0x140035211  call    PrjfFreeCommandBuffer
0x140035216  lea     r11, [rsp+2A0h+var_10]
0x14003521e  mov     eax, ebx
0x140035220  mov     rbx, [r11+20h]
0x140035224  mov     rsi, [r11+28h]
0x140035228  mov     rsp, r11
0x14003522b  pop     r15
0x14003522d  pop     r14
0x14003522f  pop     rbp
0x140035230  retn
```
