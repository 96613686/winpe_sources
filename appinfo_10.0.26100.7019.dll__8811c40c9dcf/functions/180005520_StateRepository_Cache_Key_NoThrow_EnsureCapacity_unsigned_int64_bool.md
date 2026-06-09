# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x180005520`
- end: `0x1800055bf`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `159`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007000`
- `0x180007ca0`
- `0x180008590`

## callees

- `0x180005520`
- `0x180007c78`
- `0x180010a90`
- `0x180042912`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180005540`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180005540`

## string_xrefs

- `0x180005559`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::EnsureCapacity(const void **this, const void *a2)
{
  void *v4; // rax
  void *v5; // rsi
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > this[66] )
  {
    v4 = (void *)SRCache_AllocStringBuffer((unsigned int)a2);
    v5 = v4;
    if ( !v4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v7);
      return 2147942414LL;
    }
    memcpy_0(v4, this[67], 2LL * (_QWORD)this[66]);
    wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>::reset<unsigned short *>(
      this,
      v5);
    this[67] = *this;
    this[66] = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x180005520  mov     [rsp+arg_0], rbx
0x180005525  mov     [rsp+arg_8], rsi
0x18000552a  push    rdi; int
0x18000552b  sub     rsp, 20h
0x18000552f  mov     rdi, rdx
0x180005532  mov     rbx, rcx
0x180005535  cmp     rdx, [rcx+210h]
0x18000553c  jbe     short loc_1800055AC
0x18000553e  mov     ecx, edi
0x180005540  call    cs:__imp_SRCache_AllocStringBuffer
0x180005547  nop     dword ptr [rax+rax+00h]
0x18000554c  mov     rsi, rax
0x18000554f  test    rax, rax
0x180005552  jnz     short loc_180005577
0x180005554  mov     rcx, [rsp+28h]; this
0x180005559  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005560  mov     r9d, 8007000Eh; char *
0x180005566  mov     edx, 193h; void *
0x18000556b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005570  mov     eax, 8007000Eh
0x180005575  jmp     short loc_1800055AE
0x180005577  mov     r8, [rbx+210h]
0x18000557e  mov     rcx, rsi; void *
0x180005581  mov     rdx, [rbx+218h]; Src
0x180005588  add     r8, r8; Size
0x18000558b  call    memcpy_0
0x180005590  mov     rdx, rsi
0x180005593  mov     rcx, rbx
0x180005596  call    ??$reset@PEAG@?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>::reset<ushort *>(ushort *)
0x18000559b  mov     rax, [rbx]
0x18000559e  mov     [rbx+218h], rax
0x1800055a5  mov     [rbx+210h], rdi
0x1800055ac  xor     eax, eax
0x1800055ae  mov     rbx, [rsp+28h+arg_0]
0x1800055b3  mov     rsi, [rsp+28h+arg_8]
0x1800055b8  add     rsp, 20h
0x1800055bc  pop     rdi
0x1800055bd  retn
```
