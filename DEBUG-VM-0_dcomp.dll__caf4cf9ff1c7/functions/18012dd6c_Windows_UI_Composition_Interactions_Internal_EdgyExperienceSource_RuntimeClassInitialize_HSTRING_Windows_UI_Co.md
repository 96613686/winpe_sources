# Windows::UI::Composition::Interactions::Internal::EdgyExperienceSource::RuntimeClassInitialize(HSTRING__ *,Windows::UI::Composition::Visual *)

- ea: `0x18012dd6c`
- end: `0x18012df94`
- name: `?RuntimeClassInitialize@EdgyExperienceSource@Internal@Interactions@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@PEAVVisual@456@@Z`
- size: `552`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Interactions::Internal::EdgyExperienceSource *__hidden this, HSTRING, struct Windows::UI::Composition::Visual *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18012d2f8`

## callees

- `0x18001358c`
- `0x180033c2c`
- `0x1800536d8`
- `0x18008baac`
- `0x18009a3e0`
- `0x1800bc674`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x18012dd6c`
- `0x180148c68`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18012de8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18012de8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012ddc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012de40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012dedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012df6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012ddc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012de40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012dedb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012df6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18012de79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18012de79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x18012de03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x18012de03`

## string_xrefs

- `0x18012decb`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtedgyexperiencesource.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Interactions::Internal::EdgyExperienceSource::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING a2,
        struct Windows::UI::Composition::Visual *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HSTRING *v8; // rdi
  __int64 v9; // r9
  __int64 v11; // r8
  Windows::UI::Composition::CompositionManipulation *v12; // rbx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  HSTRING v14; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING trimString; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v14 = a2;
  string = 0;
  v5 = Microsoft::WRL::Wrappers::HString::Set(&string, &v14);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 53;
LABEL_13:
    v9 = (unsigned int)v5;
    goto LABEL_14;
  }
  v8 = this + 40;
  WindowsDeleteString(this[40]);
  this[40] = 0;
  trimString = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
  v5 = WindowsTrimStringStart(string, trimString, this + 40);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 57;
    goto LABEL_13;
  }
  v14 = *v8;
  v5 = Microsoft::WRL::Wrappers::HString::Set(&string, &v14);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 59;
    goto LABEL_13;
  }
  WindowsDeleteString(*v8);
  *v8 = 0;
  trimString = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
  v5 = WindowsTrimStringEnd(string, trimString, this + 40);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 63;
    goto LABEL_13;
  }
  if ( WindowsGetStringLen(*v8) - 1 > 0x3E )
  {
    v6 = -2147024809;
    v7 = 68;
    v9 = 2147942487LL;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtedgyexperiencesource.cpp",
      (const char *)v9,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
  v5 = Windows::UI::Composition::Interactions::VisualInteractionSource::RuntimeClassInitialize(
         (Windows::UI::Composition::Interactions::VisualInteractionSource *)this,
         a3,
         0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 72;
    goto LABEL_13;
  }
  v11 = *((unsigned int *)this[31] + 36);
  if ( !(_DWORD)v11 )
    Microsoft::WRL2::FailFast::Unexpected(0);
  Windows::UI::Composition::ProxyObject::SetReferenceProperty(this[32], 8, v11);
  v12 = (Windows::UI::Composition::CompositionManipulation *)this[32];
  Windows::UI::Composition::CompositionManipulation::EdgySetEdgeId(v12, *v8);
  Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(this, 0, 2);
  Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(this, 1, 2);
  Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(this, 2, 2);
  *((_QWORD *)v12 + 22) = (unsigned __int64)(this + 37) & -(__int64)(this != 0);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18012dd6c  mov     [rsp-28h+arg_18], rbx
0x18012dd71  push    rbp
0x18012dd72  push    rsi
0x18012dd73  push    rdi
0x18012dd74  push    r12
0x18012dd76  push    r14
0x18012dd78  mov     rbp, rsp
0x18012dd7b  sub     rsp, 60h
0x18012dd7f  mov     rax, cs:__security_cookie
0x18012dd86  xor     rax, rsp
0x18012dd89  mov     [rbp+var_10], rax
0x18012dd8d  mov     rsi, rcx
0x18012dd90  mov     [rbp+var_38], rdx
0x18012dd94  lea     rdx, [rbp+var_38]; HSTRING *
0x18012dd98  mov     [rbp+string], 0
0x18012dda0  lea     rcx, [rbp+string]; newString
0x18012dda4  mov     r14, r8
0x18012dda7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18012ddac  mov     ebx, eax
0x18012ddae  test    eax, eax
0x18012ddb0  jns     short loc_18012DDBC
0x18012ddb2  mov     edx, 35h ; '5'
0x18012ddb7  jmp     loc_18012DEC4
0x18012ddbc  lea     rdi, [rsi+140h]
0x18012ddc3  mov     rcx, [rdi]; string
0x18012ddc6  call    cs:__imp_WindowsDeleteString
0x18012ddcc  mov     r9d, 1; unsigned int
0x18012ddd2  mov     qword ptr [rdi], 0
0x18012ddd9  lea     rdx, asc_1801C074C; " "
0x18012dde0  mov     [rbp+trimString], 0
0x18012dde8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18012ddec  lea     r12d, [r9+1]
0x18012ddf0  mov     r8d, r12d; unsigned int
0x18012ddf3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18012ddf8  mov     rdx, [rbp+trimString]; trimString
0x18012ddfc  mov     r8, rdi; newString
0x18012ddff  mov     rcx, [rbp+string]; string
0x18012de03  call    cs:__imp_WindowsTrimStringStart
0x18012de09  mov     ebx, eax
0x18012de0b  test    eax, eax
0x18012de0d  jns     short loc_18012DE19
0x18012de0f  lea     edx, [r12+37h]
0x18012de14  jmp     loc_18012DEC4
0x18012de19  mov     rax, [rdi]
0x18012de1c  lea     rdx, [rbp+var_38]; HSTRING *
0x18012de20  lea     rcx, [rbp+string]; newString
0x18012de24  mov     [rbp+var_38], rax
0x18012de28  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18012de2d  mov     ebx, eax
0x18012de2f  test    eax, eax
0x18012de31  jns     short loc_18012DE3D
0x18012de33  mov     edx, 3Bh ; ';'
0x18012de38  jmp     loc_18012DEC4
0x18012de3d  mov     rcx, [rdi]; string
0x18012de40  call    cs:__imp_WindowsDeleteString
0x18012de46  mov     r9d, 1; unsigned int
0x18012de4c  mov     qword ptr [rdi], 0
0x18012de53  mov     r8d, r12d; unsigned int
0x18012de56  mov     [rbp+trimString], 0
0x18012de5e  lea     rdx, asc_1801C074C; " "
0x18012de65  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18012de69  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18012de6e  mov     rdx, [rbp+trimString]; trimString
0x18012de72  mov     r8, rdi; newString
0x18012de75  mov     rcx, [rbp+string]; string
0x18012de79  call    cs:__imp_WindowsTrimStringEnd
0x18012de7f  mov     ebx, eax
0x18012de81  test    eax, eax
0x18012de83  jns     short loc_18012DE8C
0x18012de85  mov     edx, 3Fh ; '?'
0x18012de8a  jmp     short loc_18012DEC4
0x18012de8c  mov     rcx, [rdi]; string
0x18012de8f  call    cs:__imp_WindowsGetStringLen
0x18012de95  dec     eax
0x18012de97  cmp     eax, 3Eh ; '>'
0x18012de9a  jbe     short loc_18012DEAB
0x18012de9c  mov     ebx, 80070057h
0x18012dea1  mov     edx, 44h ; 'D'
0x18012dea6  mov     r9d, ebx
0x18012dea9  jmp     short loc_18012DEC7
0x18012deab  xor     r8d, r8d; bool
0x18012deae  mov     rdx, r14; struct Windows::UI::Composition::Visual *
0x18012deb1  mov     rcx, rsi; this
0x18012deb4  call    ?RuntimeClassInitialize@VisualInteractionSource@Interactions@Composition@UI@Windows@@QEAAJPEAVVisual@345@_N@Z; Windows::UI::Composition::Interactions::VisualInteractionSource::RuntimeClassInitialize(Windows::UI::Composition::Visual *,bool)
0x18012deb9  mov     ebx, eax
0x18012debb  test    eax, eax
0x18012debd  jns     short loc_18012DEE8
0x18012debf  mov     edx, 48h ; 'H'; void *
0x18012dec4  mov     r9d, eax; char *
0x18012dec7  mov     rcx, [rbp+28h]; this
0x18012decb  lea     r8, aOnecoreuapWind_211; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18012ded2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012ded7  mov     rcx, [rbp+string]; string
0x18012dedb  call    cs:__imp_WindowsDeleteString
0x18012dee1  mov     eax, ebx
0x18012dee3  jmp     loc_18012DF74
0x18012dee8  mov     rax, [rsi+0F8h]
0x18012deef  mov     r8d, [rax+90h]
0x18012def6  test    r8d, r8d
0x18012def9  jnz     short loc_18012DF03
0x18012defb  xor     ecx, ecx; char *
0x18012defd  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18012df03  mov     rcx, [rsi+100h]
0x18012df0a  mov     edx, 8
0x18012df0f  call    ?SetReferenceProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@I@Z; Windows::UI::Composition::ProxyObject::SetReferenceProperty(DCOMPOSITION_PROPERTY_ID,uint)
0x18012df14  mov     rbx, [rsi+100h]
0x18012df1b  mov     rdx, [rdi]; HSTRING
0x18012df1e  mov     rcx, rbx; this
0x18012df21  call    ?EdgySetEdgeId@CompositionManipulation@Composition@UI@Windows@@QEAAXPEAUHSTRING__@@@Z; Windows::UI::Composition::CompositionManipulation::EdgySetEdgeId(HSTRING__ *)
0x18012df26  mov     r8d, r12d
0x18012df29  xor     edx, edx
0x18012df2b  mov     rcx, rsi
0x18012df2e  call    ?SetChainingModeForAxis@VisualInteractionSource@Interactions@Composition@UI@Windows@@QEAAXW4ScrollAxis@@W4InteractionChainingMode@2345@@Z; Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(ScrollAxis,Windows::UI::Composition::Interactions::InteractionChainingMode)
0x18012df33  mov     r8d, r12d
0x18012df36  mov     edx, 1
0x18012df3b  mov     rcx, rsi
0x18012df3e  call    ?SetChainingModeForAxis@VisualInteractionSource@Interactions@Composition@UI@Windows@@QEAAXW4ScrollAxis@@W4InteractionChainingMode@2345@@Z; Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(ScrollAxis,Windows::UI::Composition::Interactions::InteractionChainingMode)
0x18012df43  mov     r8d, r12d
0x18012df46  mov     edx, r12d
0x18012df49  mov     rcx, rsi
0x18012df4c  call    ?SetChainingModeForAxis@VisualInteractionSource@Interactions@Composition@UI@Windows@@QEAAXW4ScrollAxis@@W4InteractionChainingMode@2345@@Z; Windows::UI::Composition::Interactions::VisualInteractionSource::SetChainingModeForAxis(ScrollAxis,Windows::UI::Composition::Interactions::InteractionChainingMode)
0x18012df51  lea     rcx, [rsi+128h]
0x18012df58  neg     rsi
0x18012df5b  sbb     rax, rax
0x18012df5e  and     rax, rcx
0x18012df61  mov     [rbx+0B0h], rax
0x18012df68  mov     rcx, [rbp+string]; string
0x18012df6c  call    cs:__imp_WindowsDeleteString
0x18012df72  xor     eax, eax
0x18012df74  mov     rcx, [rbp+var_10]
0x18012df78  xor     rcx, rsp; StackCookie
0x18012df7b  call    __security_check_cookie
0x18012df80  mov     rbx, [rsp+60h+arg_18]
0x18012df88  add     rsp, 60h
0x18012df8c  pop     r14
0x18012df8e  pop     r12
0x18012df90  pop     rdi
0x18012df91  pop     rsi
0x18012df92  pop     rbp
0x18012df93  retn
```
