# RdpIdEvtDriverContextCleanup(void *)

- ea: `0x18000ce80`
- end: `0x18000cf91`
- name: `?RdpIdEvtDriverContextCleanup@@YAXPEAX@Z`
- size: `273`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000ce80`
- `0x18000dbd8`
- `0x18000df20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4b`

## pseudocode

```c
void __fastcall RdpIdEvtDriverContextCleanup(void *a1)
{
  PVOID *v1; // rax
  char v2; // bl
  bool v3; // di
  _UNKNOWN **v4; // rcx
  bool v5; // si
  char CurrentThreadId; // al
  int v7; // r8d
  int v8; // edx
  bool v9; // di
  char v10; // al
  int v11; // r8d
  int v12; // edx
  int v13; // [rsp+20h] [rbp-68h]
  int v14; // [rsp+28h] [rbp-60h]

  v1 = (PVOID *)WPP_GLOBAL_Control;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v7) = v5;
    LOBYTE(v8) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      14,
      &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
      CurrentThreadId);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    v4 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( byte_180057E49 )
    __debugbreak();
  if ( v1 == &WPP_GLOBAL_Control || (*((_BYTE *)v1 + 28) & 1) == 0 || *((_BYTE *)v1 + 25) < 4u )
    v2 = 0;
  v9 = v4 != &WPP_RECORDER_INITIALIZED;
  if ( v2 || v4 != &WPP_RECORDER_INITIALIZED )
  {
    v10 = GetCurrentThreadId();
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      15,
      &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
      v10);
  }
  WppCleanupUm();
}

```

## disassembly

```asm
0x18000ce80  push    rbx
0x18000ce82  push    rbp
0x18000ce83  push    rsi
0x18000ce84  push    rdi
0x18000ce85  push    r14
0x18000ce87  push    r15
0x18000ce89  sub     rsp, 58h
0x18000ce8d  mov     rax, cs:WPP_GLOBAL_Control
0x18000ce94  lea     rbp, WPP_GLOBAL_Control
0x18000ce9b  mov     bl, 1
0x18000ce9d  cmp     rax, rbp
0x18000cea0  jz      short loc_18000CEB2
0x18000cea2  test    [rax+1Ch], bl
0x18000cea5  jz      short loc_18000CEB2
0x18000cea7  cmp     byte ptr [rax+19h], 4
0x18000ceab  jb      short loc_18000CEB2
0x18000cead  mov     dil, bl
0x18000ceb0  jmp     short loc_18000CEB5
0x18000ceb2  xor     dil, dil
0x18000ceb5  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18000cebc  lea     r14, WPP_RECORDER_INITIALIZED
0x18000cec3  cmp     rcx, r14
0x18000cec6  lea     r15, WPP_70c27897107932ddeed0a391b27b7ece_Traceguids
0x18000cecd  setnz   sil
0x18000ced1  test    dil, dil
0x18000ced4  jnz     short loc_18000CEDB
0x18000ced6  test    sil, sil
0x18000ced9  jz      short loc_18000CF1F
0x18000cedb  call    cs:__imp_GetCurrentThreadId
0x18000cee2  nop     dword ptr [rax+rax+00h]
0x18000cee7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceee  mov     r8b, sil; int
0x18000cef1  mov     dword ptr [rsp+88h+var_48], eax; char
0x18000cef5  mov     dl, dil; int
0x18000cef8  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18000cefd  mov     [rsp+88h+var_58], 0Eh; __int16
0x18000cf04  mov     r9, [rcx+28h]; int
0x18000cf08  mov     rcx, [rcx+10h]; int
0x18000cf0c  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000cf11  mov     rax, cs:WPP_GLOBAL_Control
0x18000cf18  mov     rcx, cs:WPP_RECORDER_INITIALIZED
0x18000cf1f  cmp     cs:byte_180057E49, 0
0x18000cf26  jz      short loc_18000CF29
0x18000cf28  int     3; Trap to Debugger
0x18000cf29  cmp     rax, rbp
0x18000cf2c  jz      short loc_18000CF39
0x18000cf2e  test    [rax+1Ch], bl
0x18000cf31  jz      short loc_18000CF39
0x18000cf33  cmp     byte ptr [rax+19h], 4
0x18000cf37  jnb     short loc_18000CF3B
0x18000cf39  xor     bl, bl
0x18000cf3b  cmp     rcx, r14
0x18000cf3e  setnz   dil
0x18000cf42  test    bl, bl
0x18000cf44  jnz     short loc_18000CF4B
0x18000cf46  test    dil, dil
0x18000cf49  jz      short loc_18000CF80
0x18000cf4b  call    cs:__imp_GetCurrentThreadId
0x18000cf52  nop     dword ptr [rax+rax+00h]
0x18000cf57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf5e  mov     r8b, dil; int
0x18000cf61  mov     dword ptr [rsp+88h+var_48], eax; char
0x18000cf65  mov     dl, bl; int
0x18000cf67  mov     [rsp+88h+MessageGuid], r15; MessageGuid
0x18000cf6c  mov     [rsp+88h+var_58], 0Fh; __int16
0x18000cf73  mov     r9, [rcx+28h]; int
0x18000cf77  mov     rcx, [rcx+10h]; int
0x18000cf7b  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000cf80  add     rsp, 58h
0x18000cf84  pop     r15
0x18000cf86  pop     r14
0x18000cf88  pop     rdi
0x18000cf89  pop     rsi
0x18000cf8a  pop     rbp
0x18000cf8b  pop     rbx
0x18000cf8c  jmp     WppCleanupUm
```
