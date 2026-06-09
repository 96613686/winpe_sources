# Rdp::Modern::Utils::CInflightRecorder::push(wil::FailureInfo const &)

- ea: `0x18000d734`
- end: `0x18000d823`
- name: `?push@CInflightRecorder@Utils@Modern@Rdp@@QEAAXAEBUFailureInfo@wil@@@Z`
- size: `239`
- prototype: `void(Rdp::Modern::Utils::CInflightRecorder *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d410`

## callees

- `0x18000d734`
- `0x18000d82c`
- `0x18000dc90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d7ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d7ae`

## pseudocode

```c
void __fastcall Rdp::Modern::Utils::CInflightRecorder::push(
        Rdp::Modern::Utils::CInflightRecorder *this,
        const struct wil::FailureInfo *a2)
{
  bool v3; // r15
  int v4; // ebp
  int v5; // esi
  __int64 v6; // r14
  __int64 v7; // rdi
  int v8; // ebx
  char CurrentThreadId; // al
  const wchar_t *v10; // rcx
  int v11; // [rsp+20h] [rbp-98h]
  int v12; // [rsp+28h] [rbp-90h]
  int v13; // [rsp+30h] [rbp-88h]
  __int64 v14; // [rsp+38h] [rbp-80h]

  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = *((_DWORD *)a2 + 16);
    v5 = *((_DWORD *)a2 + 1) & 8;
    v6 = *((_QWORD *)a2 + 7);
    v7 = *((_QWORD *)a2 + 3);
    v8 = *(_DWORD *)((char *)a2 + (v5 != 0 ? 4 : 0) + 8);
    CurrentThreadId = GetCurrentThreadId();
    v10 = L"status";
    if ( !v5 )
      v10 = (const wchar_t *)L"hr";
    WPP_RECORDER_AND_TRACE_SF_DSSDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v12,
      v13,
      v14,
      CurrentThreadId,
      v7,
      (__int64)v10,
      v8,
      v6,
      v4);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushInternal(this, a2);
}

```

## disassembly

```asm
0x18000d734  mov     [rsp+arg_0], rcx
0x18000d739  push    rbx
0x18000d73a  push    rbp
0x18000d73b  push    rsi
0x18000d73c  push    rdi
0x18000d73d  push    r12
0x18000d73f  push    r13
0x18000d741  push    r14
0x18000d743  push    r15
0x18000d745  sub     rsp, 78h
0x18000d749  mov     r13, rdx
0x18000d74c  mov     rax, cs:WPP_GLOBAL_Control
0x18000d753  lea     rcx, WPP_GLOBAL_Control
0x18000d75a  cmp     rax, rcx
0x18000d75d  jz      short loc_18000D770
0x18000d75f  test    byte ptr [rax+1Ch], 4
0x18000d763  jz      short loc_18000D770
0x18000d765  cmp     byte ptr [rax+19h], 4
0x18000d769  jb      short loc_18000D770
0x18000d76b  mov     r15b, 1
0x18000d76e  jmp     short loc_18000D773
0x18000d770  xor     r15b, r15b
0x18000d773  lea     rax, WPP_RECORDER_INITIALIZED
0x18000d77a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000d781  setnz   r12b
0x18000d785  test    r15b, r15b
0x18000d788  jnz     short loc_18000D78F
0x18000d78a  test    r12b, r12b
0x18000d78d  jz      short loc_18000D803
0x18000d78f  mov     esi, [rdx+4]
0x18000d792  mov     ebp, [rdx+40h]
0x18000d795  and     esi, 8
0x18000d798  mov     r14, [rdx+38h]
0x18000d79c  mov     eax, esi
0x18000d79e  mov     rdi, [rdx+18h]
0x18000d7a2  neg     eax
0x18000d7a4  sbb     rcx, rcx
0x18000d7a7  and     ecx, 4
0x18000d7aa  mov     ebx, [rcx+rdx+8]
0x18000d7ae  call    cs:__imp_GetCurrentThreadId
0x18000d7b5  nop     dword ptr [rax+rax+00h]
0x18000d7ba  mov     dword ptr [rsp+0B8h+var_50], ebp; char
0x18000d7be  lea     rdx, aHr; "hr"
0x18000d7c5  mov     [rsp+0B8h+var_58], r14; __int64
0x18000d7ca  lea     rcx, aStatus; "status"
0x18000d7d1  mov     dword ptr [rsp+0B8h+var_60], ebx; char
0x18000d7d5  test    esi, esi
0x18000d7d7  mov     r8b, r12b
0x18000d7da  cmovz   rcx, rdx
0x18000d7de  mov     dl, r15b
0x18000d7e1  mov     [rsp+0B8h+var_68], rcx; __int64
0x18000d7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7ed  mov     [rsp+0B8h+var_70], rdi; __int64
0x18000d7f2  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18000d7f6  mov     r9, [rcx+28h]
0x18000d7fa  mov     rcx, [rcx+10h]; LoggerHandle
0x18000d7fe  call    WPP_RECORDER_AND_TRACE_SF_DSSDsd
0x18000d803  mov     rcx, [rsp+0B8h+arg_0]; this
0x18000d80b  mov     rdx, r13; struct wil::FailureInfo *
0x18000d80e  add     rsp, 78h
0x18000d812  pop     r15
0x18000d814  pop     r14
0x18000d816  pop     r13
0x18000d818  pop     r12
0x18000d81a  pop     rdi
0x18000d81b  pop     rsi
0x18000d81c  pop     rbp
0x18000d81d  pop     rbx
0x18000d81e  jmp     ?pushInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAAXAEBUFailureInfo@wil@@@Z; Rdp::Modern::Utils::CInflightRecorder::pushInternal(wil::FailureInfo const &)
```
