# PrjfPreWrite

- ea: `0x140005960`
- end: `0x140005b73`
- name: `PrjfPreWrite`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002d9c`
- `0x140005960`
- `0x14000d26c`
- `0x14002b640`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140005b1b`
- `FLTMGR!FltReleaseContext` at `0x140005b33`
- `FLTMGR!FltReleaseContext` at `0x140005b48`
- `FLTMGR!FltReleaseContext` at `0x140005b1b`
- `FLTMGR!FltReleaseContext` at `0x140005b33`
- `FLTMGR!FltReleaseContext` at `0x140005b48`

## string_xrefs

- `0x140005aa6`: `onecore\base\fs\gvflt\filter\sys\readwrite.c`

## pseudocode

```c
__int64 __fastcall PrjfPreWrite(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PFLT_CONTEXT *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v6; // ebx
  char ContextFileObject; // al
  _QWORD *v8; // rdi
  ULONG IrpFlags; // ecx
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rax
  PFLT_CONTEXT v13; // rcx
  unsigned int v14; // eax
  int v16; // [rsp+20h] [rbp-60h]
  int v17; // [rsp+28h] [rbp-58h]
  __int128 v18; // [rsp+68h] [rbp-18h] BYREF
  PFLT_CONTEXT v19; // [rsp+B0h] [rbp+30h] BYREF
  PFLT_CONTEXT Context; // [rsp+C8h] [rbp+48h]

  Iopb = CallbackData->Iopb;
  v19 = 0;
  v18 = 0;
  Context = 0;
  v6 = 1;
  if ( Iopb->Parameters.Read.Length )
  {
    ContextFileObject = PrjfGetContextFileObjectEx(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v19);
    v8 = Context;
    if ( !ContextFileObject )
      goto LABEL_19;
    if ( MEMORY[0] )
      goto LABEL_19;
    IrpFlags = CallbackData->Iopb->IrpFlags;
    if ( (IrpFlags & 2) != 0 )
      goto LABEL_19;
    if ( (IrpFlags & 1) != 0 )
    {
      v6 = PrjfSynchronizeExpansionPreopWithReason(CallbackData, v16, v17, 17, (__int64)a3);
      if ( v6 == 2 )
      {
        if ( v8 )
        {
          if ( *((_DWORD *)v8 + 16) != 3 )
          {
            v12 = v8[9];
            *((_QWORD *)&v18 + 1) = v12 + 290;
            WORD1(v18) = *(_WORD *)(v12 + 288);
            LOWORD(v18) = *(_WORD *)(v12 + 288);
            if ( (BYTE8(xmmword_14001A3D0) & 4) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = BYTE8(xmmword_14001A3D0) & 4;
              LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDZ(
                770,
                v10,
                v11,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                3,
                2,
                10,
                (__int64)WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\readwrite.c",
                226,
                (__int64)&v18);
            }
          }
        }
      }
    }
    if ( (MEMORY[0x28] & 0x200) != 0 || (MEMORY[0x28] & 0x800) != 0 || (MEMORY[0x28] & 0x400) != 0 )
    {
      v13 = v19;
      if ( v19 )
      {
        v14 = 0;
        *a3 = v19;
        v13 = 0;
        v19 = 0;
        if ( v6 != 1 )
          v14 = v6;
        v6 = v14;
      }
    }
    else
    {
LABEL_19:
      v13 = v19;
    }
    if ( v8 )
    {
      FltReleaseContext(v8);
      v13 = v19;
    }
    if ( v13 )
      FltReleaseContext(v13);
  }
  return v6;
}

```

## disassembly

```asm
0x140005960  mov     [rsp-28h+arg_8], rbx
0x140005965  mov     [rsp-28h+arg_10], rsi
0x14000596a  push    rbp
0x14000596b  push    rdi
0x14000596c  push    r12
0x14000596e  push    r14
0x140005970  push    r15
0x140005972  mov     rbp, rsp
0x140005975  sub     rsp, 80h
0x14000597c  mov     rax, [rcx+10h]
0x140005980  xorps   xmm0, xmm0
0x140005983  mov     [rbp+arg_0], 0
0x14000598b  mov     r12, r8
0x14000598e  movups  [rbp+var_18], xmm0
0x140005992  mov     r15, rdx
0x140005995  mov     [rbp+Context], 0
0x14000599d  cmp     dword ptr [rax+18h], 0
0x1400059a1  mov     r14, rcx
0x1400059a4  mov     ebx, 1
0x1400059a9  mov     [rbp+var_20], 0
0x1400059b1  jz      loc_140005B54
0x1400059b7  mov     rdx, [rdx+20h]; FileObject
0x1400059bb  lea     rax, [rbp+arg_0]
0x1400059bf  mov     rcx, [r15+18h]; Instance
0x1400059c3  lea     r9, [rbp+var_20]
0x1400059c7  lea     r8, [rbp+Context]
0x1400059cb  mov     [rsp+80h+var_60], rax; int
0x1400059d0  call    PrjfGetContextFileObjectEx
0x1400059d5  mov     rdi, [rbp+Context]
0x1400059d9  mov     rsi, [rbp+var_20]
0x1400059dd  test    al, al
0x1400059df  jz      loc_140005B0F
0x1400059e5  cmp     dword ptr [rsi], 0
0x1400059e8  jnz     loc_140005B0F
0x1400059ee  mov     rax, [r14+10h]
0x1400059f2  mov     ecx, [rax]
0x1400059f4  test    cl, 2
0x1400059f7  jnz     loc_140005B0F
0x1400059fd  test    bl, cl
0x1400059ff  jz      loc_140005ADB
0x140005a05  mov     [rsp+80h+var_48], r12; __int64
0x140005a0a  lea     r8d, [rbx+2]
0x140005a0e  mov     r9d, ebx
0x140005a11  mov     [rsp+80h+var_50], 11h; int
0x140005a19  mov     rdx, r15
0x140005a1c  mov     rcx, r14; CallbackData
0x140005a1f  call    PrjfSynchronizeExpansionPreopWithReason
0x140005a24  mov     ebx, eax
0x140005a26  cmp     eax, 2
0x140005a29  jnz     loc_140005ADB
0x140005a2f  test    rdi, rdi
0x140005a32  jz      loc_140005ADB
0x140005a38  cmp     dword ptr [rdi+40h], 3
0x140005a3c  jz      loc_140005ADB
0x140005a42  mov     rax, [rdi+48h]
0x140005a46  lea     rcx, [rax+122h]
0x140005a4d  mov     qword ptr [rbp+var_18+8], rcx
0x140005a51  movzx   ecx, word ptr [rax+120h]
0x140005a58  mov     word ptr [rbp+var_18+2], cx
0x140005a5c  movzx   eax, word ptr [rax+120h]
0x140005a63  mov     word ptr [rbp+var_18], ax
0x140005a67  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140005a6d  lea     rax, WPP_RECORDER_INITIALIZED
0x140005a74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005a7b  setnz   r8b
0x140005a7f  and     dl, 4
0x140005a82  jnz     short loc_140005A89
0x140005a84  test    r8b, r8b
0x140005a87  jz      short loc_140005ADB
0x140005a89  mov     r9, cs:WPP_GLOBAL_Control
0x140005a90  lea     rax, [rbp+var_18]
0x140005a94  mov     [rsp+80h+var_30], rax
0x140005a99  mov     ecx, 302h
0x140005a9e  mov     [rsp+80h+var_38], 0E2h
0x140005aa6  lea     rax, aOnecoreBaseFsG; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140005aad  mov     [rsp+80h+var_40], rax
0x140005ab2  lea     rax, WPP_e0f66f78cb02376c02d9fc0dec322fb4_Traceguids
0x140005ab9  mov     r9, [r9+40h]
0x140005abd  mov     [rsp+80h+var_48], rax
0x140005ac2  mov     word ptr [rsp+80h+var_50], 0Ah
0x140005ac9  mov     [rsp+80h+var_58], 2
0x140005ad1  mov     byte ptr [rsp+80h+var_60], 3
0x140005ad6  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x140005adb  mov     eax, [rsi+28h]
0x140005ade  bt      eax, 9
0x140005ae2  jb      short loc_140005AF0
0x140005ae4  bt      eax, 0Bh
0x140005ae8  jb      short loc_140005AF0
0x140005aea  bt      eax, 0Ah
0x140005aee  jnb     short loc_140005B0F
0x140005af0  mov     rcx, [rbp+arg_0]
0x140005af4  test    rcx, rcx
0x140005af7  jz      short loc_140005B13
0x140005af9  xor     eax, eax
0x140005afb  mov     [r12], rcx
0x140005aff  xor     ecx, ecx
0x140005b01  cmp     ebx, 1
0x140005b04  mov     [rbp+arg_0], rcx
0x140005b08  cmovnz  eax, ebx
0x140005b0b  mov     ebx, eax
0x140005b0d  jmp     short loc_140005B13
0x140005b0f  mov     rcx, [rbp+arg_0]
0x140005b13  test    rdi, rdi
0x140005b16  jz      short loc_140005B2B
0x140005b18  mov     rcx, rdi; Context
0x140005b1b  call    cs:__imp_FltReleaseContext
0x140005b22  nop     dword ptr [rax+rax+00h]
0x140005b27  mov     rcx, [rbp+arg_0]
0x140005b2b  test    rsi, rsi
0x140005b2e  jz      short loc_140005B43
0x140005b30  mov     rcx, rsi; Context
0x140005b33  call    cs:__imp_FltReleaseContext
0x140005b3a  nop     dword ptr [rax+rax+00h]
0x140005b3f  mov     rcx, [rbp+arg_0]; Context
0x140005b43  test    rcx, rcx
0x140005b46  jz      short loc_140005B54
0x140005b48  call    cs:__imp_FltReleaseContext
0x140005b4f  nop     dword ptr [rax+rax+00h]
0x140005b54  lea     r11, [rsp+80h+var_s0]
0x140005b5c  mov     eax, ebx
0x140005b5e  mov     rbx, [r11+38h]
0x140005b62  mov     rsi, [r11+40h]
0x140005b66  mov     rsp, r11
0x140005b69  pop     r15
0x140005b6b  pop     r14
0x140005b6d  pop     r12
0x140005b6f  pop     rdi
0x140005b70  pop     rbp
0x140005b71  retn
```
