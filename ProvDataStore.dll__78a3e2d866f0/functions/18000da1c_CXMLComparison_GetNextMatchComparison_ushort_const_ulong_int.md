# CXMLComparison::GetNextMatchComparison(ushort const * *,ulong,int *)

- ea: `0x18000da1c`
- end: `0x18000db2a`
- name: `?GetNextMatchComparison@CXMLComparison@@IEAAJPEAPEBGKPEAH@Z`
- size: `270`
- prototype: `__int64 __fastcall(CXMLComparison *__hidden this, const unsigned __int16 **, unsigned int, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cf20`
- `0x18000d150`
- `0x18000f2fc`

## callees

- `0x18000a540`
- `0x18000da1c`
- `0x180010d44`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000dabd`
- `msvcrt!_wcsicmp` at `0x18000dabd`

## pseudocode

```c
__int64 __fastcall CXMLComparison::GetNextMatchComparison(
        CXMLComparison *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        int *a4)
{
  bool v4; // zf
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // rbx
  wchar_t *String1; // [rsp+40h] [rbp+8h] BYREF
  void *Src; // [rsp+58h] [rbp+20h] BYREF

  v4 = *a4 == 0;
  String1 = 0;
  Src = 0;
  if ( !v4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v9 = **((_QWORD **)this + 1);
  if ( *((_DWORD *)this + 27) )
    goto LABEL_5;
  result = (*(__int64 (**)(void))(v9 + 64))();
  *((_DWORD *)this + 27) = 1;
  while ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
    {
      *a4 = 1;
      return 0;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, wchar_t **, _QWORD))(**((_QWORD **)this + 1) + 112LL))(
               *((_QWORD *)this + 1),
               &String1,
               0);
    if ( (int)result < 0 )
      return result;
    v11 = 0;
    if ( a3 )
    {
      while ( _wcsicmp(String1, a2[v11]) )
      {
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= a3 )
          goto LABEL_13;
      }
    }
    else
    {
LABEL_13:
      if ( (_DWORD)v11 == a3 )
      {
        std::wstring::assign((__int64 *)this + 2, (char *)String1);
        result = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
                   *((_QWORD *)this + 1),
                   &Src,
                   0);
        if ( (int)result < 0 )
          return result;
        std::wstring::assign((__int64 *)this + 6, (char *)Src);
        return 0;
      }
    }
    v9 = **((_QWORD **)this + 1);
LABEL_5:
    result = (*(__int64 (**)(void))(v9 + 72))();
  }
  return result;
}

```

## disassembly

```asm
0x18000da1c  mov     rax, rsp
0x18000da1f  mov     [rax+10h], rbx
0x18000da23  mov     [rax+18h], rbp
0x18000da27  push    rsi
0x18000da28  push    rdi
0x18000da29  push    r14
0x18000da2b  sub     rsp, 20h
0x18000da2f  cmp     dword ptr [r9], 0
0x18000da33  mov     rsi, r9
0x18000da36  mov     ebp, r8d
0x18000da39  mov     qword ptr [rax+8], 0
0x18000da41  mov     r14, rdx
0x18000da44  mov     qword ptr [rax+20h], 0
0x18000da4c  mov     rdi, rcx
0x18000da4f  jz      short loc_18000DA56
0x18000da51  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000da56  cmp     dword ptr [rdi+6Ch], 0
0x18000da5a  mov     rcx, [rdi+8]
0x18000da5e  mov     rax, [rcx]
0x18000da61  jnz     short loc_18000DA75
0x18000da63  mov     rax, [rax+40h]
0x18000da67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da6c  mov     dword ptr [rdi+6Ch], 1
0x18000da73  jmp     short loc_18000DA7E
0x18000da75  mov     rax, [rax+48h]
0x18000da79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7e  test    eax, eax
0x18000da80  js      loc_18000DB17
0x18000da86  cmp     eax, 1
0x18000da89  jnz     short loc_18000DA92
0x18000da8b  mov     [rsi], eax
0x18000da8d  jmp     loc_18000DB15
0x18000da92  mov     rcx, [rdi+8]
0x18000da96  lea     rdx, [rsp+38h+String1]
0x18000da9b  xor     r8d, r8d
0x18000da9e  mov     rax, [rcx]
0x18000daa1  mov     rax, [rax+70h]
0x18000daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daaa  test    eax, eax
0x18000daac  js      short loc_18000DB17
0x18000daae  xor     ebx, ebx
0x18000dab0  test    ebp, ebp
0x18000dab2  jz      short loc_18000DACD
0x18000dab4  mov     rdx, [r14+rbx*8]; String2
0x18000dab8  mov     rcx, [rsp+38h+String1]; String1
0x18000dabd  call    cs:__imp__wcsicmp
0x18000dac3  test    eax, eax
0x18000dac5  jz      short loc_18000DAD1
0x18000dac7  inc     ebx
0x18000dac9  cmp     ebx, ebp
0x18000dacb  jb      short loc_18000DAB4
0x18000dacd  cmp     ebx, ebp
0x18000dacf  jz      short loc_18000DADA
0x18000dad1  mov     rcx, [rdi+8]
0x18000dad5  mov     rax, [rcx]
0x18000dad8  jmp     short loc_18000DA75
0x18000dada  mov     rdx, [rsp+38h+String1]; Src
0x18000dadf  lea     rcx, [rdi+10h]; void *
0x18000dae3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000dae8  mov     rcx, [rdi+8]
0x18000daec  lea     rdx, [rsp+38h+Src]
0x18000daf1  xor     r8d, r8d
0x18000daf4  mov     rax, [rcx]
0x18000daf7  mov     rax, [rax+80h]
0x18000dafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db03  test    eax, eax
0x18000db05  js      short loc_18000DB17
0x18000db07  mov     rdx, [rsp+38h+Src]; Src
0x18000db0c  lea     rcx, [rdi+30h]; void *
0x18000db10  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000db15  xor     eax, eax
0x18000db17  mov     rbx, [rsp+38h+arg_8]
0x18000db1c  mov     rbp, [rsp+38h+arg_10]
0x18000db21  add     rsp, 20h
0x18000db25  pop     r14
0x18000db27  pop     rdi
0x18000db28  pop     rsi
0x18000db29  retn
```
