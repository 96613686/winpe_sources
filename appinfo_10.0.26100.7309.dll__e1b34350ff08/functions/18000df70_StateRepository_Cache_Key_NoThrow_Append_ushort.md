# StateRepository::Cache::Key_NoThrow::Append(ushort)

- ea: `0x18000df70`
- end: `0x18000e053`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJG@Z`
- size: `227`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d828`

## callees

- `0x180007c78`
- `0x18000df70`
- `0x180010bd0`
- `0x1800444a2`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000df9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000df9c`

## string_xrefs

- `0x18000dfb5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000dfd1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(StateRepository::Cache::Key_NoThrow *this)
{
  unsigned __int64 v2; // rdi
  void *v3; // rax
  void *v4; // rsi
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 65) + 2LL;
  if ( v2 > *((_QWORD *)this + 66) )
  {
    v3 = (void *)SRCache_AllocStringBuffer((unsigned int)v2);
    v4 = v3;
    if ( !v3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v6);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v7);
      return 2147942414LL;
    }
    memcpy_0(v3, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
      this,
      v4);
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = v2;
  }
  *(_DWORD *)(*((_QWORD *)this + 67) + 2LL * (*((_QWORD *)this + 65))++) = 94;
  return 0;
}

```

## disassembly

```asm
0x18000df70  mov     [rsp+arg_0], rbx
0x18000df75  mov     [rsp+arg_8], rsi
0x18000df7a  push    rdi; int
0x18000df7b  sub     rsp, 20h
0x18000df7f  mov     rdi, [rcx+208h]
0x18000df86  mov     rbx, rcx
0x18000df89  add     rdi, 2
0x18000df8d  cmp     rdi, [rcx+210h]
0x18000df94  jbe     loc_18000E024
0x18000df9a  mov     ecx, edi
0x18000df9c  call    cs:__imp_SRCache_AllocStringBuffer
0x18000dfa3  nop     dword ptr [rax+rax+00h]
0x18000dfa8  mov     rsi, rax
0x18000dfab  test    rax, rax
0x18000dfae  jnz     short loc_18000DFEF
0x18000dfb0  mov     rcx, [rsp+28h]; this
0x18000dfb5  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dfbc  mov     r9d, 8007000Eh; char *
0x18000dfc2  mov     edx, 193h; void *
0x18000dfc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfcc  mov     rcx, [rsp+28h]; this
0x18000dfd1  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000dfd8  mov     r9d, 8007000Eh; char *
0x18000dfde  mov     edx, 16Dh; void *
0x18000dfe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfe8  mov     eax, 8007000Eh
0x18000dfed  jmp     short loc_18000E042
0x18000dfef  mov     r8, [rbx+210h]
0x18000dff6  mov     rcx, rsi; void *
0x18000dff9  mov     rdx, [rbx+218h]; Src
0x18000e000  add     r8, r8; Size
0x18000e003  call    memcpy_0
0x18000e008  mov     rdx, rsi
0x18000e00b  mov     rcx, rbx
0x18000e00e  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x18000e013  mov     rax, [rbx]
0x18000e016  mov     [rbx+218h], rax
0x18000e01d  mov     [rbx+210h], rdi
0x18000e024  mov     rcx, [rbx+208h]
0x18000e02b  mov     rax, [rbx+218h]
0x18000e032  mov     dword ptr [rax+rcx*2], 5Eh ; '^'
0x18000e039  inc     qword ptr [rbx+208h]
0x18000e040  xor     eax, eax
0x18000e042  mov     rbx, [rsp+28h+arg_0]
0x18000e047  mov     rsi, [rsp+28h+arg_8]
0x18000e04c  add     rsp, 20h
0x18000e050  pop     rdi
0x18000e051  retn
```
