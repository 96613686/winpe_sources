# Windows::ApplicationModel::Resources::Core::CResourceQualifier::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,uchar,uchar,double)

- ea: `0x18007dcfc`
- end: `0x18007ddfa`
- name: `?RuntimeClassInitialize@CResourceQualifier@Core@Resources@ApplicationModel@Windows@@QEAAJPEAUHSTRING__@@0EEN@Z`
- size: `254`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceQualifier *__hidden this, HSTRING, HSTRING, unsigned __int8, unsigned __int8, double)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800ae57c`

## callees

- `0x18000c8a0`
- `0x18002c8d0`
- `0x18006997c`
- `0x180069b68`
- `0x18007dcfc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dd69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007dd2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007dd2c`

## string_xrefs

- `0x18007dd4e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x18007dd94`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceQualifier::RuntimeClassInitialize(
        Windows::ApplicationModel::Resources::Core::CResourceQualifier *this,
        HSTRING a2,
        HSTRING a3,
        char a4,
        unsigned __int8 a5,
        double a6)
{
  HRESULT v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  HSTRING newString[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  HSTRING v16; // [rsp+70h] [rbp+38h] BYREF

  v16 = a3;
  string = 0;
  newString[0] = 0;
  v8 = WindowsDuplicateString(a2, newString);
  v9 = Windows::Internal::String::FreeAndAssignOnSuccess(v8, newString[0], &string);
  v10 = v9;
  if ( v9 >= 0 )
  {
    newString[0] = 0;
    v11 = Windows::Internal::String::Initialize((Windows::Internal::String *)newString, &v16);
    v10 = v11;
    if ( v11 >= 0 )
    {
      *((_QWORD *)this + 8) = string;
      string = 0;
      *((HSTRING *)this + 9) = newString[0];
      newString[0] = 0;
      *((_BYTE *)this + 80) = a4;
      *((_BYTE *)this + 81) = a5;
      *((double *)this + 11) = a6;
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x372,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)newString);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
    if ( string )
      WindowsDeleteString(string);
  }
  return v10;
}

```

## disassembly

```asm
0x18007dcfc  mov     [rsp-20h+arg_10], r8
0x18007dd01  push    rbp
0x18007dd02  push    rbx
0x18007dd03  push    rsi
0x18007dd04  push    rdi
0x18007dd05  mov     rbp, rsp
0x18007dd08  sub     rsp, 38h
0x18007dd0c  mov     sil, r9b
0x18007dd0f  mov     rax, rdx
0x18007dd12  mov     rdi, rcx
0x18007dd15  mov     [rbp+string], 0
0x18007dd1d  mov     [rbp+newString], 0
0x18007dd25  lea     rdx, [rbp+newString]; newString
0x18007dd29  mov     rcx, rax; string
0x18007dd2c  call    cs:__imp_WindowsDuplicateString
0x18007dd32  lea     r8, [rbp+string]; HSTRING *
0x18007dd36  mov     rdx, [rbp+newString]; HSTRING
0x18007dd3a  mov     ecx, eax; int
0x18007dd3c  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18007dd41  mov     ebx, eax
0x18007dd43  test    eax, eax
0x18007dd45  jns     short loc_18007DD72
0x18007dd47  mov     rcx, [rbp+20h]; this
0x18007dd4b  mov     r9d, eax; char *
0x18007dd4e  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18007dd55  mov     edx, 36Fh; void *
0x18007dd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dd5f  nop
0x18007dd60  mov     rcx, [rbp+string]; string
0x18007dd64  test    rcx, rcx
0x18007dd67  jz      short loc_18007DD70
0x18007dd69  call    cs:__imp_WindowsDeleteString
0x18007dd6f  nop
0x18007dd70  jmp     short loc_18007DDEF
0x18007dd72  mov     [rbp+newString], 0
0x18007dd7a  lea     rdx, [rbp+arg_10]; HSTRING *
0x18007dd7e  lea     rcx, [rbp+newString]; this
0x18007dd82  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18007dd87  mov     ebx, eax
0x18007dd89  test    eax, eax
0x18007dd8b  jns     short loc_18007DDA7
0x18007dd8d  mov     rcx, [rbp+20h]; this
0x18007dd91  mov     r9d, eax; char *
0x18007dd94  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18007dd9b  mov     edx, 372h; void *
0x18007dda0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dda5  jmp     short loc_18007DDDD
0x18007dda7  mov     rax, [rbp+string]
0x18007ddab  mov     [rdi+40h], rax
0x18007ddaf  mov     [rbp+string], 0
0x18007ddb7  mov     rax, [rbp+newString]
0x18007ddbb  mov     [rdi+48h], rax
0x18007ddbf  mov     [rbp+newString], 0
0x18007ddc7  mov     [rdi+50h], sil
0x18007ddcb  mov     al, [rbp+arg_20]
0x18007ddce  mov     [rdi+51h], al
0x18007ddd1  movsd   xmm0, [rbp+arg_28]
0x18007ddd6  movsd   qword ptr [rdi+58h], xmm0
0x18007dddb  xor     ebx, ebx
0x18007dddd  lea     rcx, [rbp+newString]; this
0x18007dde1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007dde6  lea     rcx, [rbp+string]; this
0x18007ddea  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007ddef  mov     eax, ebx
0x18007ddf1  add     rsp, 38h
0x18007ddf5  pop     rdi
0x18007ddf6  pop     rsi
0x18007ddf7  pop     rbx
0x18007ddf8  pop     rbp
0x18007ddf9  retn
```
