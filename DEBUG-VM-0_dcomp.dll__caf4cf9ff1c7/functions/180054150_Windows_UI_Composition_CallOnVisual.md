# Windows::UI::Composition::CallOnVisual

- ea: `0x180054150`
- end: `0x1800542b2`
- name: `Windows::UI::Composition::CallOnVisual`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180052d7c`

## callees

- `0x18001358c`
- `0x180054150`
- `0x1800554dc`
- `0x1800555f0`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800541f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054266`

## string_xrefs

- `0x18005424e`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositiondiagnosticsinterop.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CallOnVisual(
        __int64 a1,
        __int64 a2,
        Windows::UI::Composition::CompositionObject *a3,
        unsigned int a4,
        HSTRING string)
{
  HSTRING v5; // rsi
  int Comment; // eax
  unsigned int v10; // ebx
  int v11; // eax
  HSTRING v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-20h]
  __int64 v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v5 = string;
  v20 = 0;
  v19 = 0;
  *(_BYTE *)string = 1;
  Windows::UI::Composition::VisualCommon::ToApi<Windows::UI::Composition::IVisual>(a2, &v20);
  Windows::UI::Composition::VisualCommon::ToApi<Windows::UI::Composition::IVisual>(a3, &v19);
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  Comment = Windows::UI::Composition::CompositionObject::GetComment(a3, &string);
  v10 = Comment;
  if ( Comment < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositiondiagnosticsinterop.cpp",
      (const char *)(unsigned int)Comment,
      v18);
    WindowsDeleteString(string);
    v16 = v19;
    string = 0;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v10;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, HSTRING))(*(_QWORD *)a1 + 24LL))(
            a1,
            v20,
            v19,
            a4,
            string);
    v12 = string;
    *(_BYTE *)v5 = v11 == 0;
    WindowsDeleteString(v12);
    v13 = v19;
    string = 0;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180054150  push    rbp
0x180054152  push    rbx
0x180054153  push    rsi
0x180054154  push    rdi
0x180054155  push    r14
0x180054157  mov     rbp, rsp
0x18005415a  sub     rsp, 40h
0x18005415e  mov     rsi, [rbp+string]
0x180054162  mov     rax, rdx
0x180054165  mov     rdi, rcx
0x180054168  mov     [rbp+var_8], 0
0x180054170  lea     rdx, [rbp+var_8]
0x180054174  mov     [rbp+var_10], 0
0x18005417c  mov     rcx, rax
0x18005417f  mov     r14d, r9d
0x180054182  mov     byte ptr [rsi], 1
0x180054185  mov     rbx, r8
0x180054188  call    ??$ToApi@UIVisual@Composition@UI@Windows@@@VisualCommon@Composition@UI@Windows@@SAXPEAV0123@V?$ComPtrRef@V?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::UI::Composition::VisualCommon::ToApi<Windows::UI::Composition::IVisual>(Windows::UI::Composition::VisualCommon *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>>)
0x18005418d  lea     rdx, [rbp+var_10]
0x180054191  mov     rcx, rbx
0x180054194  call    ??$ToApi@UIVisual@Composition@UI@Windows@@@VisualCommon@Composition@UI@Windows@@SAXPEAV0123@V?$ComPtrRef@V?$ComPtr@UIVisual@Composition@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::UI::Composition::VisualCommon::ToApi<Windows::UI::Composition::IVisual>(Windows::UI::Composition::VisualCommon *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::IVisual>>)
0x180054199  xor     ecx, ecx; string
0x18005419b  mov     [rbp+string], 0
0x1800541a3  call    cs:__imp_WindowsDeleteString
0x1800541a9  lea     rdx, [rbp+string]; HSTRING *
0x1800541ad  mov     [rbp+string], 0
0x1800541b5  mov     rcx, rbx; this
0x1800541b8  call    ?GetComment@CompositionObject@Composition@UI@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionObject::GetComment(HSTRING__ * *)
0x1800541bd  mov     ebx, eax
0x1800541bf  test    eax, eax
0x1800541c1  js      loc_18005424A
0x1800541c7  mov     rcx, [rbp+string]
0x1800541cb  mov     r9d, r14d
0x1800541ce  mov     rax, [rdi]
0x1800541d1  mov     r8, [rbp+var_10]
0x1800541d5  mov     rdx, [rbp+var_8]
0x1800541d9  mov     qword ptr [rsp+40h+var_20], rcx
0x1800541de  mov     rcx, rdi
0x1800541e1  mov     rax, [rax+18h]
0x1800541e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541ea  mov     rcx, [rbp+string]; string
0x1800541ee  test    eax, eax
0x1800541f0  setz    al
0x1800541f3  mov     [rsi], al
0x1800541f5  call    cs:__imp_WindowsDeleteString
0x1800541fb  mov     rcx, [rbp+var_10]
0x1800541ff  mov     [rbp+string], 0
0x180054207  test    rcx, rcx
0x18005420a  jz      short loc_180054220
0x18005420c  mov     [rbp+var_10], 0
0x180054214  mov     rax, [rcx]
0x180054217  mov     rax, [rax+10h]
0x18005421b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054220  mov     rcx, [rbp+var_8]
0x180054224  test    rcx, rcx
0x180054227  jz      short loc_18005423D
0x180054229  mov     [rbp+var_8], 0
0x180054231  mov     rax, [rcx]
0x180054234  mov     rax, [rax+10h]
0x180054238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005423d  xor     eax, eax
0x18005423f  add     rsp, 40h
0x180054243  pop     r14
0x180054245  pop     rdi
0x180054246  pop     rsi
0x180054247  pop     rbx
0x180054248  pop     rbp
0x180054249  retn
0x18005424a  mov     rcx, [rbp+28h]; this
0x18005424e  lea     r8, aOnecoreuapWind_182; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180054255  mov     r9d, ebx; char *
0x180054258  mov     edx, 5Dh ; ']'; void *
0x18005425d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054262  mov     rcx, [rbp+string]; string
0x180054266  call    cs:__imp_WindowsDeleteString
0x18005426c  mov     rcx, [rbp+var_10]
0x180054270  mov     [rbp+string], 0
0x180054278  test    rcx, rcx
0x18005427b  jz      short loc_180054291
0x18005427d  mov     [rbp+var_10], 0
0x180054285  mov     rax, [rcx]
0x180054288  mov     rax, [rax+10h]
0x18005428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054291  mov     rcx, [rbp+var_8]
0x180054295  test    rcx, rcx
0x180054298  jz      short loc_1800542AE
0x18005429a  mov     [rbp+var_8], 0
0x1800542a2  mov     rax, [rcx]
0x1800542a5  mov     rax, [rax+10h]
0x1800542a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542ae  mov     eax, ebx
0x1800542b0  jmp     short loc_18005423F
```
