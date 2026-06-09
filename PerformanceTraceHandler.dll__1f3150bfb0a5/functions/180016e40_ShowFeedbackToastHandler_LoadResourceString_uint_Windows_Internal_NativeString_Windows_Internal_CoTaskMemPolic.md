# ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x180016e40`
- end: `0x180016ea5`
- name: `?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001642c`
- `0x1800166a0`
- `0x180016868`
- `0x18001874c`

## callees

- `0x180011660`
- `0x180012b48`
- `0x180016e40`

## pseudocode

```c
__int64 __fastcall ShowFeedbackToastHandler::LoadResourceString(__int64 a1, unsigned int a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v7; // [rsp+58h] [rbp+20h] BYREF

  v6 = a1;
  v7 = 0;
  LOWORD(v6) = 0;
  v4 = -2147467259;
  if ( Windows::Internal::ResourceString::FindAndSize(
         (HINSTANCE)0x180000000LL,
         a2,
         (unsigned __int16)a3,
         (const unsigned __int16 **)&v7,
         (unsigned __int16 *)&v6) )
  {
    return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                           a3,
                           v7,
                           (unsigned __int16)v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180016e40  mov     r11, rsp
0x180016e43  mov     [r11+10h], rbx
0x180016e47  mov     [r11+8], rcx
0x180016e4b  push    rdi
0x180016e4c  sub     rsp, 30h
0x180016e50  xor     eax, eax
0x180016e52  mov     qword ptr [r11+20h], 0
0x180016e5a  mov     word ptr [rsp+38h+arg_0], ax
0x180016e5f  lea     r9, [r11+20h]; unsigned __int16 **
0x180016e63  lea     rax, [r11+8]
0x180016e67  mov     rdi, r8
0x180016e6a  lea     rcx, cs:180000000h; hModule
0x180016e71  mov     [r11-18h], rax
0x180016e75  mov     ebx, 80004005h
0x180016e7a  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180016e7f  test    al, al
0x180016e81  jz      short loc_180016E98
0x180016e83  movzx   r8d, word ptr [rsp+38h+arg_0]
0x180016e89  mov     rcx, rdi
0x180016e8c  mov     rdx, [rsp+38h+arg_18]
0x180016e91  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180016e96  mov     ebx, eax
0x180016e98  mov     eax, ebx
0x180016e9a  mov     rbx, [rsp+38h+arg_8]
0x180016e9f  add     rsp, 30h
0x180016ea3  pop     rdi
0x180016ea4  retn
```
