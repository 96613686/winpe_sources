# Windows::UI::Composition::EffectInstance::SetCompiledEffect(Windows::UI::Composition::ICompiledEffect const *)

- ea: `0x180013b80`
- end: `0x180013bc3`
- name: `?SetCompiledEffect@EffectInstance@Composition@UI@Windows@@UEAAJPEBUICompiledEffect@234@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::UI::Composition::EffectInstance *__hidden this, const struct Windows::UI::Composition::ICompiledEffect *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013b80`
- `0x180013bcc`
- `0x18001dc90`

## string_xrefs

- `0x180013bad`: `onecoreuap\windows\dwm\effects\compiler\effectinstance.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::EffectInstance::SetCompiledEffect(
        Windows::UI::Composition::EffectInstance *this,
        const struct Windows::UI::Composition::ICompiledEffect *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5[2]; // [rsp+20h] [rbp-18h] BYREF
  const struct Windows::UI::Composition::ICompiledEffect *v6; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)v5 = this;
  v6 = a2;
  v2 = wil::ResultFromException__Windows::UI::Composition::EffectInstance::SetCompiledEffect_::_4_::_lambda_1___(v5);
  v3 = v2;
  if ( v2 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\effectinstance.cpp",
      (const char *)(unsigned int)v2,
      v5[0]);
  return v3;
}

```

## disassembly

```asm
0x180013b80  push    rbx
0x180013b82  sub     rsp, 30h
0x180013b86  mov     qword ptr [rsp+38h+var_18], rcx; int
0x180013b8b  lea     rcx, [rsp+38h+var_18]
0x180013b90  mov     [rsp+38h+var_10], rdx
0x180013b95  call    wil__ResultFromException__Windows__UI__Composition__EffectInstance__SetCompiledEffect____4____lambda_1___
0x180013b9a  mov     ebx, eax
0x180013b9c  test    eax, eax
0x180013b9e  js      short loc_180013BA8
0x180013ba0  mov     eax, ebx
0x180013ba2  add     rsp, 30h
0x180013ba6  pop     rbx
0x180013ba7  retn
0x180013ba8  mov     rcx, [rsp+38h]; this
0x180013bad  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x180013bb4  mov     r9d, ebx; char *
0x180013bb7  mov     edx, 13Ch; void *
0x180013bbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bc1  jmp     short loc_180013BA0
```
