# CONFIG_OBJECT_EXTENSION::RequestConfigurationOutput(IExtensionContext *)

- ea: `0x18001ded0`
- end: `0x18001dfa4`
- name: `?RequestConfigurationOutput@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a850`

## callees

- `0x18001ded0`
- `0x180036010`

## string_xrefs

- `0x18001df39`: `CONFIG`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::RequestConfigurationOutput(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2)
{
  int v2; // ebx
  int v3; // eax
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  v5 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v3 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v5);
  v2 = v3;
  if ( v3 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, &v6);
    if ( v2 < 0 )
      goto LABEL_9;
    v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v6 + 56LL))(
           v6,
           L"OUTPUT",
           L"CONFIG");
    if ( v2 < 0 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( v3 == -2147024846 )
LABEL_8:
    v2 = 1;
LABEL_9:
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v5 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001ded0  mov     [rsp+arg_0], rcx
0x18001ded5  push    rbx
0x18001ded6  sub     rsp, 20h
0x18001deda  mov     [rsp+28h+arg_8], 0
0x18001dee3  mov     r8, rdx
0x18001dee6  mov     [rsp+28h+arg_0], 0
0x18001deef  test    rdx, rdx
0x18001def2  jnz     short loc_18001DEFE
0x18001def4  mov     ebx, 80070057h
0x18001def9  jmp     loc_18001DF9C
0x18001defe  mov     rax, [rdx]
0x18001df01  mov     rcx, r8
0x18001df04  lea     rdx, [rsp+28h+arg_0]
0x18001df09  mov     rax, [rax+18h]
0x18001df0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df12  mov     ebx, eax
0x18001df14  test    eax, eax
0x18001df16  js      short loc_18001DF5B
0x18001df18  mov     rcx, [rsp+28h+arg_0]
0x18001df1d  lea     rdx, [rsp+28h+arg_8]
0x18001df22  mov     rax, [rcx]
0x18001df25  mov     rax, [rax+30h]
0x18001df29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2e  mov     ebx, eax
0x18001df30  test    eax, eax
0x18001df32  js      short loc_18001DF67
0x18001df34  mov     rcx, [rsp+28h+arg_8]
0x18001df39  lea     r8, aConfig; "CONFIG"
0x18001df40  lea     rdx, aOutput; "OUTPUT"
0x18001df47  mov     rax, [rcx]
0x18001df4a  mov     rax, [rax+38h]
0x18001df4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df53  mov     ebx, eax
0x18001df55  test    eax, eax
0x18001df57  js      short loc_18001DF67
0x18001df59  jmp     short loc_18001DF62
0x18001df5b  cmp     eax, 80070032h
0x18001df60  jnz     short loc_18001DF67
0x18001df62  mov     ebx, 1
0x18001df67  mov     rcx, [rsp+28h+arg_0]
0x18001df6c  test    rcx, rcx
0x18001df6f  jz      short loc_18001DF86
0x18001df71  mov     rax, [rcx]
0x18001df74  mov     rax, [rax+10h]
0x18001df78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df7d  mov     [rsp+28h+arg_0], 0
0x18001df86  mov     rcx, [rsp+28h+arg_8]
0x18001df8b  test    rcx, rcx
0x18001df8e  jz      short loc_18001DF9C
0x18001df90  mov     rax, [rcx]
0x18001df93  mov     rax, [rax+10h]
0x18001df97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df9c  mov     eax, ebx
0x18001df9e  add     rsp, 20h
0x18001dfa2  pop     rbx
0x18001dfa3  retn
```
