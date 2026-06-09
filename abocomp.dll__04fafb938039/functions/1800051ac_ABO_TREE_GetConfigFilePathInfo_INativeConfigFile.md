# ABO_TREE::GetConfigFilePathInfo(INativeConfigFile *)

- ea: `0x1800051ac`
- end: `0x180005263`
- name: `?GetConfigFilePathInfo@ABO_TREE@@AEAAJPEAVINativeConfigFile@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(ABO_TREE *__hidden this, struct INativeConfigFile *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004f98`

## callees

- `0x1800051ac`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005250`
- `OLEAUT32!__imp_SysFreeString` at `0x180005250`
- `iisutil!IsPathUnc` at `0x18000521f`
- `iisutil!IsPathUnc` at `0x18000521f`

## pseudocode

```c
__int64 __fastcall ABO_TREE::GetConfigFilePathInfo(ABO_TREE *this, struct INativeConfigFile *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  bstrString = 0;
  if ( a2 )
  {
    v3 = (**(__int64 (__fastcall ***)(struct INativeConfigFile *, GUID *, __int64 *))a2)(
           a2,
           &IID_IAppHostConfigFile,
           &v5);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v5 + 32LL))(v5, &bstrString);
      if ( v3 >= 0 )
        v3 = IsPathUnc(bstrString, (int *)this + 16);
    }
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v5 = 0;
    }
    if ( bstrString )
      SysFreeString(bstrString);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800051ac  mov     [rsp+arg_0], rbx
0x1800051b1  push    rdi
0x1800051b2  sub     rsp, 20h
0x1800051b6  mov     [rsp+28h+arg_8], 0
0x1800051bf  mov     r9, rdx
0x1800051c2  mov     [rsp+28h+bstrString], 0
0x1800051cb  mov     rdi, rcx
0x1800051ce  test    rdx, rdx
0x1800051d1  jnz     short loc_1800051DA
0x1800051d3  mov     ebx, 80070057h
0x1800051d8  jmp     short loc_180005256
0x1800051da  mov     rax, [rdx]
0x1800051dd  lea     r8, [rsp+28h+arg_8]
0x1800051e2  lea     rdx, IID_IAppHostConfigFile
0x1800051e9  mov     rcx, r9
0x1800051ec  mov     rax, [rax]
0x1800051ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f4  mov     ebx, eax
0x1800051f6  test    eax, eax
0x1800051f8  js      short loc_180005227
0x1800051fa  mov     rcx, [rsp+28h+arg_8]
0x1800051ff  lea     rdx, [rsp+28h+bstrString]
0x180005204  mov     rax, [rcx]
0x180005207  mov     rax, [rax+20h]
0x18000520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005210  mov     ebx, eax
0x180005212  test    eax, eax
0x180005214  js      short loc_180005227
0x180005216  mov     rcx, [rsp+28h+bstrString]
0x18000521b  lea     rdx, [rdi+40h]
0x18000521f  call    cs:__imp_?IsPathUnc@@YAJPEBGPEAH@Z; IsPathUnc(ushort const *,int *)
0x180005225  mov     ebx, eax
0x180005227  mov     rcx, [rsp+28h+arg_8]
0x18000522c  test    rcx, rcx
0x18000522f  jz      short loc_180005246
0x180005231  mov     rax, [rcx]
0x180005234  mov     rax, [rax+10h]
0x180005238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523d  mov     [rsp+28h+arg_8], 0
0x180005246  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000524b  test    rcx, rcx
0x18000524e  jz      short loc_180005256
0x180005250  call    cs:__imp_SysFreeString
0x180005256  mov     eax, ebx
0x180005258  mov     rbx, [rsp+28h+arg_0]
0x18000525d  add     rsp, 20h
0x180005261  pop     rdi
0x180005262  retn
```
