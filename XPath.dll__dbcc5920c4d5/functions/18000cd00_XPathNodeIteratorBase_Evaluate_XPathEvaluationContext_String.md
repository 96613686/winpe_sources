# XPathNodeIteratorBase::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000cd00`
- end: `0x18000cd79`
- name: `?Evaluate@XPathNodeIteratorBase@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `121`
- prototype: `int(XPathNodeIteratorBase *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bfd0`

## callees

- `0x18000cd00`
- `0x18000e594`
- `0x180010ee0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNodeIteratorBase::Evaluate(
        XPathNodeIteratorBase *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  __int64 *v3; // rdi
  __int64 result; // rax
  __int64 v6; // rax
  XPathNavigatorInternal *v7; // rax
  unsigned __int16 *v8; // rdx
  int v9; // eax
  unsigned int v10; // ecx
  unsigned __int16 *v11; // [rsp+30h] [rbp+8h] BYREF

  v3 = (__int64 *)((char *)this - 8);
  result = (*(__int64 (__fastcall **)(char *, struct XPathEvaluationContext *))(*((_QWORD *)this - 1) + 104LL))(
             (char *)this - 8,
             a2);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result )
    {
      v8 = (unsigned __int16 *)&qword_180016F98;
    }
    else
    {
      v6 = *v3;
      v11 = 0;
      v7 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(__int64 *))(v6 + 72))(v3);
      result = XPathNavigatorInternal::GetValue(v7, (const unsigned __int16 **)&v11);
      if ( (int)result < 0 )
        return result;
      v8 = v11;
    }
    v9 = String::Initialize(a3, v8);
    v10 = 0;
    if ( v9 < 0 )
      return (unsigned int)v9;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18000cd00  mov     [rsp+arg_8], rbx
0x18000cd05  push    rdi
0x18000cd06  sub     rsp, 20h
0x18000cd0a  lea     rdi, [rcx-8]
0x18000cd0e  mov     rbx, r8
0x18000cd11  mov     rax, [rdi]
0x18000cd14  mov     rcx, rdi
0x18000cd17  mov     rax, [rax+68h]
0x18000cd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd20  test    eax, eax
0x18000cd22  js      short loc_18000CD6E
0x18000cd24  jnz     short loc_18000CD56
0x18000cd26  mov     rax, [rdi]
0x18000cd29  mov     rcx, rdi
0x18000cd2c  mov     [rsp+28h+arg_0], 0
0x18000cd35  mov     rax, [rax+48h]
0x18000cd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3e  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x18000cd43  mov     rcx, rax; this
0x18000cd46  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000cd4b  test    eax, eax
0x18000cd4d  js      short loc_18000CD6E
0x18000cd4f  mov     rdx, [rsp+28h+arg_0]
0x18000cd54  jmp     short loc_18000CD5D
0x18000cd56  lea     rdx, qword_180016F98; unsigned __int16 *
0x18000cd5d  mov     rcx, rbx; this
0x18000cd60  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000cd65  xor     ecx, ecx
0x18000cd67  test    eax, eax
0x18000cd69  cmovs   ecx, eax
0x18000cd6c  mov     eax, ecx
0x18000cd6e  mov     rbx, [rsp+28h+arg_8]
0x18000cd73  add     rsp, 20h
0x18000cd77  pop     rdi
0x18000cd78  retn
```
