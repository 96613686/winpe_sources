# Windows::UI::Composition::CompositionAnimationGroup::StopAnimations(Windows::UI::Composition::CompositionObject *)

- ea: `0x1800c96a0`
- end: `0x1800c97a2`
- name: `?StopAnimations@CompositionAnimationGroup@Composition@UI@Windows@@QEAAJPEAVCompositionObject@234@@Z`
- size: `258`
- prototype: `int(Windows::UI::Composition::CompositionAnimationGroup *__hidden this, struct Windows::UI::Composition::CompositionObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800c9590`

## callees

- `0x18001358c`
- `0x180074480`
- `0x1800744bc`
- `0x1800c96a0`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c96da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9763`

## string_xrefs

- `0x1800c9718`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`
- `0x1800c9776`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositionanimationgroup.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionAnimationGroup::StopAnimations(
        Windows::UI::Composition::CompositionAnimationGroup *this,
        struct Windows::UI::Composition::CompositionObject *a2)
{
  _QWORD *i; // rdi
  Windows::UI::Composition::CompositionAnimation *v4; // rbx
  HSTRING v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v10; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    for ( i = (_QWORD *)*((_QWORD *)this + 23); i; i = (_QWORD *)*i )
    {
      v4 = (Windows::UI::Composition::CompositionAnimation *)i[2];
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      Windows::UI::Composition::CompositionAnimation::GetTarget(v4, &string);
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)string,
                            0,
                            v5) )
      {
        v6 = -2147024809;
        v7 = 328;
        v8 = 2147942487LL;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
          (const char *)v8,
          v11);
        WindowsDeleteString(string);
        return v6;
      }
      v10 = (*(__int64 (__fastcall **)(struct Windows::UI::Composition::CompositionObject *, HSTRING))(*(_QWORD *)a2 + 176LL))(
              a2,
              string);
      v6 = v10;
      if ( v10 < 0 )
      {
        v8 = (unsigned int)v10;
        v7 = 330;
        goto LABEL_6;
      }
      WindowsDeleteString(string);
    }
    return 0;
  }
  else
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositionanimationgroup.cpp",
      (const char *)0x80070057LL,
      v11);
    return v6;
  }
}

```

## disassembly

```asm
0x1800c96a0  mov     [rsp+arg_0], rbx
0x1800c96a5  mov     [rsp+arg_10], rsi
0x1800c96aa  push    rdi; int
0x1800c96ab  sub     rsp, 20h
0x1800c96af  mov     rsi, rdx
0x1800c96b2  test    rdx, rdx
0x1800c96b5  jz      loc_1800C9771
0x1800c96bb  mov     rdi, [rcx+0B8h]
0x1800c96c2  test    rdi, rdi
0x1800c96c5  jz      loc_1800C979E
0x1800c96cb  mov     rbx, [rdi+10h]
0x1800c96cf  xor     ecx, ecx; string
0x1800c96d1  mov     [rsp+28h+string], 0
0x1800c96da  call    cs:__imp_WindowsDeleteString
0x1800c96e0  lea     rdx, [rsp+28h+string]; HSTRING *
0x1800c96e5  mov     [rsp+28h+string], 0
0x1800c96ee  mov     rcx, rbx; this
0x1800c96f1  call    ?GetTarget@CompositionAnimation@Composition@UI@Windows@@QEAAXPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionAnimation::GetTarget(HSTRING__ * *)
0x1800c96f6  mov     rcx, [rsp+28h+string]; this
0x1800c96fb  xor     edx, edx; HSTRING
0x1800c96fd  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800c9702  test    eax, eax
0x1800c9704  jnz     short loc_1800C9741
0x1800c9706  mov     ebx, 80070057h
0x1800c970b  mov     edx, 148h; void *
0x1800c9710  mov     r9d, ebx; char *
0x1800c9713  mov     rcx, [rsp+28h]; this
0x1800c9718  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800c971f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9724  mov     rcx, [rsp+28h+string]; string
0x1800c9729  call    cs:__imp_WindowsDeleteString
0x1800c972f  mov     eax, ebx
0x1800c9731  mov     rbx, [rsp+28h+arg_0]
0x1800c9736  mov     rsi, [rsp+28h+arg_10]
0x1800c973b  add     rsp, 20h
0x1800c973f  pop     rdi
0x1800c9740  retn
0x1800c9741  mov     rax, [rsi]
0x1800c9744  mov     rcx, rsi
0x1800c9747  mov     rdx, [rsp+28h+string]
0x1800c974c  mov     rax, [rax+0B0h]
0x1800c9753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9758  mov     ebx, eax
0x1800c975a  test    eax, eax
0x1800c975c  js      short loc_1800C9791
0x1800c975e  mov     rcx, [rsp+28h+string]; string
0x1800c9763  call    cs:__imp_WindowsDeleteString
0x1800c9769  mov     rdi, [rdi]
0x1800c976c  jmp     loc_1800C96C2
0x1800c9771  mov     rcx, [rsp+28h]; this
0x1800c9776  lea     r8, aOnecoreuapWind_213; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800c977d  mov     ebx, 80070057h
0x1800c9782  mov     edx, 13Ah; void *
0x1800c9787  mov     r9d, ebx; char *
0x1800c978a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c978f  jmp     short loc_1800C972F
0x1800c9791  mov     r9d, eax
0x1800c9794  mov     edx, 14Ah
0x1800c9799  jmp     loc_1800C9713
0x1800c979e  xor     eax, eax
0x1800c97a0  jmp     short loc_1800C9731
```
