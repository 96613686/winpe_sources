# _lambda_7e2c5cc4db30a8bd4cdec04a7259f421_::operator()

- ea: `0x18002ad84`
- end: `0x18002ae35`
- name: `_lambda_7e2c5cc4db30a8bd4cdec04a7259f421_::operator()`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e880`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18001dc6c`
- `0x18002ad84`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ade2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ade2`

## string_xrefs

- `0x18002ae01`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall lambda_7e2c5cc4db30a8bd4cdec04a7259f421_::operator()(HSTRING *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v11; // [rsp+38h] [rbp+10h] BYREF

  v11 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
  v2 = CloudExperienceHostCreateElevatedObject(
         &GUID_86c815aa_4888_4063_b0ab_03c49f788be4,
         &GUID_426317b8_c7d2_4647_ad76_2554806561b6,
         &v11);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = v11;
    v6 = *(__int64 (__fastcall **)(void *, PCWSTR))(*(_QWORD *)v11 + 104LL);
    StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
    v2 = v6(v5, StringRawBuffer);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v3 = 0;
      goto LABEL_7;
    }
    v4 = 374;
  }
  else
  {
    v4 = 373;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v2,
    v9);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
  return v3;
}

```

## disassembly

```asm
0x18002ad84  mov     rax, rsp
0x18002ad87  mov     [rax+8], rbx
0x18002ad8b  mov     [rax+18h], rsi
0x18002ad8f  mov     [rax+10h], rdx
0x18002ad93  push    rdi; int
0x18002ad94  sub     rsp, 20h
0x18002ad98  mov     rsi, rcx
0x18002ad9b  mov     qword ptr [rax+10h], 0
0x18002ada3  lea     rcx, [rax+10h]
0x18002ada7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002adac  lea     r8, [rsp+28h+arg_8]; void **
0x18002adb1  lea     rdx, _GUID_426317b8_c7d2_4647_ad76_2554806561b6; struct _GUID *
0x18002adb8  lea     rcx, _GUID_86c815aa_4888_4063_b0ab_03c49f788be4; struct _GUID *
0x18002adbf  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18002adc4  mov     ebx, eax
0x18002adc6  test    eax, eax
0x18002adc8  jns     short loc_18002ADD1
0x18002adca  mov     edx, 175h
0x18002adcf  jmp     short loc_18002AE01
0x18002add1  mov     rdi, [rsp+28h+arg_8]
0x18002add6  mov     rax, [rdi]
0x18002add9  mov     rbx, [rax+68h]
0x18002addd  xor     edx, edx; length
0x18002addf  mov     rcx, [rsi]; string
0x18002ade2  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ade8  mov     rdx, rax
0x18002adeb  mov     rcx, rdi
0x18002adee  mov     rax, rbx
0x18002adf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adf6  mov     ebx, eax
0x18002adf8  test    eax, eax
0x18002adfa  jns     short loc_18002AE17
0x18002adfc  mov     edx, 176h; void *
0x18002ae01  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002ae08  mov     r9d, eax; char *
0x18002ae0b  mov     rcx, [rsp+28h]; this
0x18002ae10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ae15  jmp     short loc_18002AE19
0x18002ae17  xor     ebx, ebx
0x18002ae19  lea     rcx, [rsp+28h+arg_8]
0x18002ae1e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ae23  mov     eax, ebx
0x18002ae25  mov     rbx, [rsp+28h+arg_0]
0x18002ae2a  mov     rsi, [rsp+28h+arg_10]
0x18002ae2f  add     rsp, 20h
0x18002ae33  pop     rdi
0x18002ae34  retn
```
