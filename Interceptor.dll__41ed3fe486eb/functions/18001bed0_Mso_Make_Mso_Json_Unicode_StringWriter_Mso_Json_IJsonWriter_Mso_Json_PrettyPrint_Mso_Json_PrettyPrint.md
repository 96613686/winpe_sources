# Mso::Make<Mso::Json::Unicode::StringWriter,Mso::Json::IJsonWriter,Mso::Json::PrettyPrint>(Mso::Json::PrettyPrint &&)

- ea: `0x18001bed0`
- end: `0x18001bf9d`
- name: `??$Make@VStringWriter@Unicode@Json@Mso@@UIJsonWriter@34@W4PrettyPrint@34@@Mso@@YA?AV?$TCntPtr@UIJsonWriter@Json@Mso@@@0@$$QEAW4PrettyPrint@Json@0@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800198c0`

## callees

- `0x1800122fc`
- `0x180012318`
- `0x18001be7c`
- `0x18001bed0`
- `0x18001bfd0`
- `0x18002b3c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001beef`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001beef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Mso::Make<Mso::Json::Unicode::StringWriter,Mso::Json::IJsonWriter,enum Mso::Json::PrettyPrint>(
        _QWORD *a1,
        int *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  int v6; // esi
  void (__fastcall ***v7)(_QWORD); // rdx
  __int64 v8; // rcx
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v4 = malloc(0x98u);
  v5 = v4;
  if ( !v4 )
    CrashWithRecoveryOnOOM(0x1F65259Du);
  v6 = *a2;
  v4[2] = 1;
  *(_QWORD *)v4 = &Mso::Json::Unicode::StringWriter::`vftable';
  *((_OWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 4) = 0;
  *((_QWORD *)v4 + 5) = 7;
  *((_WORD *)v4 + 8) = 0;
  v7 = *(void (__fastcall ****)(_QWORD))Mso::Json::MakeStringRefOutput<wchar_t>(&v10);
  if ( !v7 )
    CrashWithRecovery(0x1E3C3843u, 0);
  Mso::Json::TWriter<wchar_t>::TWriter<wchar_t>((__int64)(v5 + 12), v7, v6);
  v8 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  }
  *a1 = v5;
  return a1;
}

```

## disassembly

```asm
0x18001bed0  mov     [rsp+arg_0], rbx
0x18001bed5  mov     [rsp+arg_8], rbp
0x18001beda  mov     [rsp+arg_18], rsi
0x18001bedf  push    rdi
0x18001bee0  sub     rsp, 20h
0x18001bee4  mov     rsi, rdx
0x18001bee7  mov     rdi, rcx
0x18001beea  mov     ecx, 98h; Size
0x18001beef  call    cs:__imp_malloc
0x18001bef5  mov     rbx, rax
0x18001bef8  xor     ebp, ebp
0x18001befa  test    rax, rax
0x18001befd  jz      loc_18001BF92
0x18001bf03  mov     esi, [rsi]
0x18001bf05  mov     dword ptr [rax+8], 1
0x18001bf0c  lea     rax, ??_7StringWriter@Unicode@Json@Mso@@6B@; const Mso::Json::Unicode::StringWriter::`vftable'
0x18001bf13  mov     [rbx], rax
0x18001bf16  lea     rdx, [rbx+10h]
0x18001bf1a  xorps   xmm0, xmm0
0x18001bf1d  movups  xmmword ptr [rdx], xmm0
0x18001bf20  mov     [rdx+10h], rbp
0x18001bf24  mov     qword ptr [rdx+18h], 7
0x18001bf2c  mov     [rdx], bp
0x18001bf2f  lea     rcx, [rsp+28h+arg_10]
0x18001bf34  call    ??$MakeStringRefOutput@_W@Json@Mso@@YA?AV?$TCntRef@U?$TIOutput@_W@Json@Mso@@@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::MakeStringRefOutput<wchar_t>(std::wstring &)
0x18001bf39  mov     rdx, [rax]; struct CrashContext *
0x18001bf3c  test    rdx, rdx
0x18001bf3f  jz      short loc_18001BF84
0x18001bf41  lea     rcx, [rbx+30h]
0x18001bf45  mov     r8d, esi
0x18001bf48  call    ??0?$TWriter@_W@Json@Mso@@QEAA@AEAU?$TIOutput@_W@12@W4PrettyPrint@12@@Z; Mso::Json::TWriter<wchar_t>::TWriter<wchar_t>(Mso::Json::TIOutput<wchar_t> &,Mso::Json::PrettyPrint)
0x18001bf4d  mov     rcx, [rsp+28h+arg_10]
0x18001bf52  test    rcx, rcx
0x18001bf55  jz      short loc_18001BF69
0x18001bf57  mov     [rsp+28h+arg_10], rbp
0x18001bf5c  mov     rax, [rcx]
0x18001bf5f  mov     rax, [rax+8]
0x18001bf63  call    cs:__guard_dispatch_icall_fptr
0x18001bf69  mov     [rdi], rbx
0x18001bf6c  mov     rax, rdi
0x18001bf6f  mov     rbx, [rsp+28h+arg_0]
0x18001bf74  mov     rbp, [rsp+28h+arg_8]
0x18001bf79  mov     rsi, [rsp+28h+arg_18]
0x18001bf7e  add     rsp, 20h
0x18001bf82  pop     rdi
0x18001bf83  retn
0x18001bf84  mov     ecx, 1E3C3843h; unsigned int
0x18001bf89  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18001bf8f  jmp     short $+2
0x18001bf91  nop
0x18001bf92  mov     ecx, 1F65259Dh; unsigned int
0x18001bf97  call    ?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
```
