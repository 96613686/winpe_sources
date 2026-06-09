# CAudioTimeCompression::SetInputProperty(int,int)

- ea: `0x18004fae0`
- end: `0x18004fbaa`
- name: `?SetInputProperty@CAudioTimeCompression@@QEAAJHH@Z`
- size: `202`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b690`
- `0x18004eba0`

## callees

- `0x18004f270`
- `0x18004fae0`
- `0x18004fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fb44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioTimeCompression::SetInputProperty(CAudioTimeCompression *this, signed int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int16 v7; // cx
  int v8; // edi

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( a2 && a2 <= 96000 )
  {
    v7 = 6;
    if ( !a3 )
      v7 = 2;
    if ( v7 == *((_WORD *)this + 3) || (v8 = 0, a2 != *((_DWORD *)this + 2)) )
    {
      EnterCriticalSection(v6);
      *((_BYTE *)this + 22) = 0;
      LeaveCriticalSection(v6);
      v8 = CAudioTimeCompression::OnInputFormatChange(this, a2, a3);
      if ( v8 >= 0 )
        CAudioTimeCompression::Start(this);
    }
  }
  else
  {
    v8 = -2147024809;
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004fae0  mov     [rsp+arg_8], rbx
0x18004fae5  mov     [rsp+arg_10], rbp
0x18004faea  push    rsi
0x18004faeb  push    rdi
0x18004faec  push    r14
0x18004faee  sub     rsp, 20h
0x18004faf2  mov     r14d, r8d
0x18004faf5  mov     ebp, edx
0x18004faf7  mov     rbx, rcx
0x18004fafa  lea     rsi, [rcx+0E0h]
0x18004fb01  mov     [rsp+38h+arg_0], rsi
0x18004fb06  mov     rcx, rsi; lpCriticalSection
0x18004fb09  call    cs:__imp_EnterCriticalSection
0x18004fb10  nop     dword ptr [rax+rax+00h]
0x18004fb15  nop
0x18004fb16  test    ebp, ebp
0x18004fb18  jz      short loc_18004FB80
0x18004fb1a  cmp     ebp, 17700h
0x18004fb20  jg      short loc_18004FB80
0x18004fb22  movzx   eax, word ptr [rbx+6]
0x18004fb26  test    r14d, r14d
0x18004fb29  mov     ecx, 6
0x18004fb2e  jnz     short loc_18004FB35
0x18004fb30  mov     ecx, 2
0x18004fb35  cmp     cx, ax
0x18004fb38  jz      short loc_18004FB41
0x18004fb3a  xor     edi, edi
0x18004fb3c  cmp     ebp, [rbx+8]
0x18004fb3f  jz      short loc_18004FB85
0x18004fb41  mov     rcx, rsi; lpCriticalSection
0x18004fb44  call    cs:__imp_EnterCriticalSection
0x18004fb4b  nop     dword ptr [rax+rax+00h]
0x18004fb50  mov     byte ptr [rbx+16h], 0
0x18004fb54  mov     rcx, rsi; lpCriticalSection
0x18004fb57  call    cs:__imp_LeaveCriticalSection
0x18004fb5e  nop     dword ptr [rax+rax+00h]
0x18004fb63  mov     r8d, r14d; int
0x18004fb66  mov     edx, ebp; int
0x18004fb68  mov     rcx, rbx; this
0x18004fb6b  call    ?OnInputFormatChange@CAudioTimeCompression@@IEAAJHH@Z; CAudioTimeCompression::OnInputFormatChange(int,int)
0x18004fb70  mov     edi, eax
0x18004fb72  test    eax, eax
0x18004fb74  js      short loc_18004FB85
0x18004fb76  mov     rcx, rbx; this
0x18004fb79  call    ?Start@CAudioTimeCompression@@IEAAJXZ; CAudioTimeCompression::Start(void)
0x18004fb7e  jmp     short loc_18004FB85
0x18004fb80  mov     edi, 80070057h
0x18004fb85  mov     rcx, rsi; lpCriticalSection
0x18004fb88  call    cs:__imp_LeaveCriticalSection
0x18004fb8f  nop     dword ptr [rax+rax+00h]
0x18004fb94  mov     eax, edi
0x18004fb96  mov     rbx, [rsp+38h+arg_8]
0x18004fb9b  mov     rbp, [rsp+38h+arg_10]
0x18004fba0  add     rsp, 20h
0x18004fba4  pop     r14
0x18004fba6  pop     rdi
0x18004fba7  pop     rsi
0x18004fba8  retn
```
