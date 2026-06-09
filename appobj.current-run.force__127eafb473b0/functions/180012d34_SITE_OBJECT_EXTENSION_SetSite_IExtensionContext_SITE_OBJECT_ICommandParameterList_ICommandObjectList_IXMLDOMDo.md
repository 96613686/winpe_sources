# SITE_OBJECT_EXTENSION::SetSite(IExtensionContext *,SITE_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180012d34`
- end: `0x180012ee4`
- name: `?SetSite@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVSITE_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `432`
- prototype: `int(SITE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct SITE_OBJECT *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011690`

## callees

- `0x180012450`
- `0x180012d34`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180012e32`
- `msvcrt!wcsstr` at `0x180012e32`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::SetSite(
        SITE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct SITE_OBJECT *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        struct IXMLDOMDocument *a6)
{
  struct INativeConfigurationElement *v6; // rcx
  int v10; // ebx
  int v11; // r12d
  int v12; // eax
  SITE_OBJECT_EXTENSION *v13; // rcx
  int v14; // eax
  unsigned __int16 *v16; // [rsp+40h] [rbp-20h] BYREF
  __int128 v17; // [rsp+48h] [rbp-18h] BYREF
  struct INativeConfigurationElement *v18; // [rsp+90h] [rbp+30h] BYREF
  wchar_t *Str; // [rsp+98h] [rbp+38h] BYREF

  v16 = 0;
  v6 = 0;
  v18 = 0;
  Str = 0;
  v17 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v10 = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, struct INativeConfigurationElement **))(*(_QWORD *)a3 + 48LL))(
            a3,
            &v18);
    if ( v10 >= 0 )
    {
      v11 = 0;
      v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)a4 + 40LL))(
              a4,
              L"bindings",
              &v16);
      v10 = v12;
      if ( v12 >= 0 )
      {
        if ( *v16 )
        {
          v11 = 1;
          v10 = SITE_OBJECT_EXTENSION::SetBindingInformation(v13, a2, v18, v16, 0);
          if ( v10 < 0 )
            goto LABEL_14;
        }
LABEL_11:
        v14 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)a4 + 40LL))(
                a4,
                L"name",
                &Str);
        v10 = v14;
        if ( v14 < 0 )
        {
          if ( v14 != -2147023483 )
            goto LABEL_14;
        }
        else if ( wcsstr(Str, L"/") )
        {
          *(_QWORD *)&v17 = L"name";
          v10 = -2147024809;
          *((_QWORD *)&v17 + 1) = Str;
          (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            2147942487LL,
            3221226476LL,
            &v17,
            0);
          goto LABEL_14;
        }
        v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct SITE_OBJECT *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, int))(*(_QWORD *)a2 + 168LL))(
                a2,
                a3,
                a4,
                a5,
                a6,
                v11);
        goto LABEL_14;
      }
      if ( v12 == -2147023483 )
        goto LABEL_11;
    }
LABEL_14:
    v6 = v18;
    goto LABEL_18;
  }
  v10 = -2147024809;
LABEL_18:
  if ( v6 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012d34  mov     [rsp-28h+arg_10], rbx
0x180012d39  mov     [rsp-28h+arg_18], rsi
0x180012d3e  mov     [rsp-28h+arg_0], rcx
0x180012d43  push    rbp
0x180012d44  push    rdi
0x180012d45  push    r12
0x180012d47  push    r13
0x180012d49  push    r14
0x180012d4b  mov     rbp, rsp
0x180012d4e  sub     rsp, 60h
0x180012d52  xor     r13d, r13d
0x180012d55  xorps   xmm0, xmm0
0x180012d58  mov     [rbp+var_20], r13
0x180012d5c  mov     ecx, r13d
0x180012d5f  mov     [rbp+arg_0], rcx
0x180012d63  mov     rdi, r9
0x180012d66  mov     [rbp+Str], r13
0x180012d6a  mov     r14, r8
0x180012d6d  mov     rsi, rdx
0x180012d70  movups  [rbp+var_18], xmm0
0x180012d74  test    rdx, rdx
0x180012d77  jz      loc_180012EB3
0x180012d7d  test    r8, r8
0x180012d80  jz      loc_180012EB3
0x180012d86  test    r9, r9
0x180012d89  jz      loc_180012EB3
0x180012d8f  cmp     [rbp+arg_20], r13
0x180012d93  jz      loc_180012EB3
0x180012d99  mov     rax, [r8]
0x180012d9c  lea     rdx, [rbp+arg_0]
0x180012da0  mov     rcx, r8
0x180012da3  mov     rax, [rax+30h]
0x180012da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dac  mov     ebx, eax
0x180012dae  test    eax, eax
0x180012db0  js      loc_180012E78
0x180012db6  mov     rax, [rdi]
0x180012db9  lea     r8, [rbp+var_20]
0x180012dbd  lea     rdx, aBindings_0; "bindings"
0x180012dc4  mov     rcx, rdi
0x180012dc7  mov     r12d, r13d
0x180012dca  mov     rax, [rax+28h]
0x180012dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dd3  mov     ebx, eax
0x180012dd5  test    eax, eax
0x180012dd7  js      short loc_180012E00
0x180012dd9  mov     r9, [rbp+var_20]; unsigned __int16 *
0x180012ddd  cmp     [r9], r13w
0x180012de1  jz      short loc_180012E07
0x180012de3  mov     r8, [rbp+arg_0]; struct INativeConfigurationElement *
0x180012de7  lea     r12d, [r13+1]
0x180012deb  mov     rdx, rsi; struct IExtensionContext *
0x180012dee  mov     [rsp+60h+var_40], r13d; int
0x180012df3  call    ?SetBindingInformation@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVINativeConfigurationElement@@PEBGH@Z; SITE_OBJECT_EXTENSION::SetBindingInformation(IExtensionContext *,INativeConfigurationElement *,ushort const *,int)
0x180012df8  mov     ebx, eax
0x180012dfa  test    eax, eax
0x180012dfc  js      short loc_180012E78
0x180012dfe  jmp     short loc_180012E07
0x180012e00  cmp     eax, 80070585h
0x180012e05  jnz     short loc_180012E78
0x180012e07  mov     rax, [rdi]
0x180012e0a  lea     r8, [rbp+Str]
0x180012e0e  lea     rdx, aName_0; "name"
0x180012e15  mov     rcx, rdi
0x180012e18  mov     rax, [rax+28h]
0x180012e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e21  mov     ebx, eax
0x180012e23  test    eax, eax
0x180012e25  js      short loc_180012E7E
0x180012e27  mov     rcx, [rbp+Str]; Str
0x180012e2b  lea     rdx, SubStr; "/"
0x180012e32  call    cs:__imp_wcsstr
0x180012e38  test    rax, rax
0x180012e3b  jz      short loc_180012E85
0x180012e3d  lea     rax, aName_0; "name"
0x180012e44  mov     [rsp+60h+var_40], r13d
0x180012e49  mov     qword ptr [rbp+var_18], rax
0x180012e4d  lea     r9, [rbp+var_18]
0x180012e51  mov     rax, [rbp+Str]
0x180012e55  mov     ebx, 80070057h
0x180012e5a  mov     qword ptr [rbp+var_18+8], rax
0x180012e5e  mov     r8d, 0C00003ECh
0x180012e64  mov     rax, [rsi]
0x180012e67  mov     edx, ebx
0x180012e69  mov     rcx, rsi
0x180012e6c  mov     rax, [rax+90h]
0x180012e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e78  mov     rcx, [rbp+arg_0]
0x180012e7c  jmp     short loc_180012EB8
0x180012e7e  cmp     eax, 80070585h
0x180012e83  jnz     short loc_180012E78
0x180012e85  mov     rax, [rsi]
0x180012e88  mov     r8, rdi
0x180012e8b  mov     rcx, [rbp+arg_28]
0x180012e8f  mov     rdx, r14
0x180012e92  mov     r9, [rbp+arg_20]
0x180012e96  mov     [rsp+60h+var_38], r12d
0x180012e9b  mov     rax, [rax+0A8h]
0x180012ea2  mov     qword ptr [rsp+60h+var_40], rcx
0x180012ea7  mov     rcx, rsi
0x180012eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eaf  mov     ebx, eax
0x180012eb1  jmp     short loc_180012E78
0x180012eb3  mov     ebx, 80070057h
0x180012eb8  test    rcx, rcx
0x180012ebb  jz      short loc_180012EC9
0x180012ebd  mov     rax, [rcx]
0x180012ec0  mov     rax, [rax+10h]
0x180012ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec9  lea     r11, [rsp+60h+var_s0]
0x180012ece  mov     eax, ebx
0x180012ed0  mov     rbx, [r11+40h]
0x180012ed4  mov     rsi, [r11+48h]
0x180012ed8  mov     rsp, r11
0x180012edb  pop     r14
0x180012edd  pop     r13
0x180012edf  pop     r12
0x180012ee1  pop     rdi
0x180012ee2  pop     rbp
0x180012ee3  retn
```
