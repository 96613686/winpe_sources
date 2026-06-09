# SITE_CUSTOM_PROVIDER::Create(ushort const *)

- ea: `0x180013e0c`
- end: `0x180013ead`
- name: `?Create@SITE_CUSTOM_PROVIDER@@QEAAJPEBG@Z`
- size: `161`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012718`
- `0x180012cb0`

## callees

- `0x180013e0c`
- `0x180014830`
- `0x180015124`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013e71`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013e71`

## string_xrefs

- `0x180013e51`: `virtualDirectoryDefaults`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::Create(SITE_CUSTOM_PROVIDER *this, const unsigned __int16 *a2)
{
  int ControlProperties; // ecx

  if ( a2 )
  {
    ControlProperties = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 3) + 32LL))(
                          *((_QWORD *)this + 3),
                          L"applicationDefaults",
                          (char *)this + 48);
    if ( ControlProperties >= 0 )
    {
      ControlProperties = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 3) + 32LL))(
                            *((_QWORD *)this + 3),
                            L"virtualDirectoryDefaults",
                            (char *)this + 40);
      if ( ControlProperties >= 0 )
      {
        ControlProperties = STRU::Copy((SITE_CUSTOM_PROVIDER *)((char *)this + 56), a2);
        if ( ControlProperties >= 0 )
        {
          ControlProperties = SITE_CUSTOM_PROVIDER::GenerateControlProperties(this);
          if ( ControlProperties >= 0 )
          {
            ControlProperties = SITE_CUSTOM_PROVIDER::GetDefaultApplicationPool(this);
            if ( ControlProperties == -2147024894 )
              return 0;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ControlProperties;
}

```

## disassembly

```asm
0x180013e0c  mov     [rsp+arg_0], rbx
0x180013e11  push    rdi
0x180013e12  sub     rsp, 20h
0x180013e16  mov     rdi, rdx
0x180013e19  mov     rbx, rcx
0x180013e1c  test    rdx, rdx
0x180013e1f  jnz     short loc_180013E28
0x180013e21  mov     ecx, 80070057h
0x180013e26  jmp     short loc_180013EA0
0x180013e28  mov     rcx, [rcx+18h]
0x180013e2c  lea     r8, [rbx+30h]
0x180013e30  lea     rdx, aApplicationdef; "applicationDefaults"
0x180013e37  mov     rax, [rcx]
0x180013e3a  mov     rax, [rax+20h]
0x180013e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e43  mov     ecx, eax
0x180013e45  test    eax, eax
0x180013e47  js      short loc_180013EA0
0x180013e49  mov     rcx, [rbx+18h]
0x180013e4d  lea     r8, [rbx+28h]
0x180013e51  lea     rdx, aVirtualdirecto; "virtualDirectoryDefaults"
0x180013e58  mov     rax, [rcx]
0x180013e5b  mov     rax, [rax+20h]
0x180013e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e64  mov     ecx, eax
0x180013e66  test    eax, eax
0x180013e68  js      short loc_180013EA0
0x180013e6a  lea     rcx, [rbx+38h]
0x180013e6e  mov     rdx, rdi
0x180013e71  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013e77  mov     ecx, eax
0x180013e79  test    eax, eax
0x180013e7b  js      short loc_180013EA0
0x180013e7d  mov     rcx, rbx; this
0x180013e80  call    ?GenerateControlProperties@SITE_CUSTOM_PROVIDER@@AEAAJXZ; SITE_CUSTOM_PROVIDER::GenerateControlProperties(void)
0x180013e85  mov     ecx, eax
0x180013e87  test    eax, eax
0x180013e89  js      short loc_180013EA0
0x180013e8b  mov     rcx, rbx; this
0x180013e8e  call    ?GetDefaultApplicationPool@SITE_CUSTOM_PROVIDER@@AEAAJXZ; SITE_CUSTOM_PROVIDER::GetDefaultApplicationPool(void)
0x180013e93  mov     ecx, eax
0x180013e95  xor     eax, eax
0x180013e97  cmp     ecx, 80070002h
0x180013e9d  cmovz   ecx, eax
0x180013ea0  mov     rbx, [rsp+28h+arg_0]
0x180013ea5  mov     eax, ecx
0x180013ea7  add     rsp, 20h
0x180013eab  pop     rdi
0x180013eac  retn
```
