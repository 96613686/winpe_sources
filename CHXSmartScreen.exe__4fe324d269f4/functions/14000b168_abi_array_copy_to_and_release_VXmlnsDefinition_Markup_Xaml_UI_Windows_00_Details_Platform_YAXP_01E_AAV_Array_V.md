# ??$__abi_array_copy_to_and_release@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Details@Platform@@YAXP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@PEAPEAXPEAI@Z

- ea: `0x14000b168`
- end: `0x14000b245`
- name: `??$__abi_array_copy_to_and_release@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Details@Platform@@YAXP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@PEAPEAXPEAI@Z`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e800`
- `0x1400114b4`

## callees

- `0x14000b168`
- `0x14000bf34`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x14000b23e`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x14000b23e`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x14000b237`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x14000b237`

## pseudocode

```c
void __fastcall Platform::Details::__abi_array_copy_to_and_release<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
        __int64 a1,
        char **a2,
        _DWORD *a3)
{
  __int64 v5; // rdx

  v5 = 0;
  if ( !a1 )
  {
    *a2 = 0;
    *a3 = 0;
    return;
  }
  if ( !a2 || !a3 )
  {
    __abi_WinRTraiseNullReferenceException();
    JUMPOUT(0x14000B244LL);
  }
  if ( *(_DWORD *)(a1 + 72) )
  {
    if ( *(_QWORD *)(a1 + 80) )
    {
      if ( !*(_BYTE *)(a1 + 76) && *(_QWORD *)(a1 + 88) && *(_DWORD *)(*(_QWORD *)(a1 + 88) + 12LL) == 1 )
      {
        *a2 = *(char **)(a1 + 80);
        *a3 = *(_DWORD *)(a1 + 72);
        *(_DWORD *)(a1 + 72) = 0;
        *(_BYTE *)(a1 + 76) = 0;
        *(_QWORD *)(a1 + 80) = 0;
        goto LABEL_16;
      }
      if ( *(_BYTE *)(a1 + 76) || *(_QWORD *)(a1 + 88) && *(int *)(*(_QWORD *)(a1 + 88) + 12LL) > 1 )
      {
        *a2 = Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(
                *(_QWORD *)(a1 + 80),
                *(_DWORD *)(a1 + 72));
        *a3 = *(_DWORD *)(a1 + 72);
        goto LABEL_16;
      }
    }
    __abi_WinRTraiseFailureException();
    __debugbreak();
  }
  *a2 = 0;
  *a3 = 0;
LABEL_16:
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, v5);
}

```

## disassembly

```asm
0x14000b168  mov     [rsp+arg_0], rbx
0x14000b16d  mov     [rsp+arg_8], rsi
0x14000b172  push    rdi
0x14000b173  sub     rsp, 20h
0x14000b177  mov     rsi, rdx
0x14000b17a  mov     rdi, r8
0x14000b17d  xor     edx, edx
0x14000b17f  mov     rbx, rcx
0x14000b182  test    rcx, rcx
0x14000b185  jnz     short loc_14000B19D
0x14000b187  mov     [rsi], rdx
0x14000b18a  mov     [r8], edx
0x14000b18d  mov     rbx, [rsp+28h+arg_0]
0x14000b192  mov     rsi, [rsp+28h+arg_8]
0x14000b197  add     rsp, 20h
0x14000b19b  pop     rdi
0x14000b19c  retn
0x14000b19d  test    rsi, rsi
0x14000b1a0  jz      loc_14000B23E
0x14000b1a6  test    rdi, rdi
0x14000b1a9  jz      loc_14000B23E
0x14000b1af  cmp     [rcx+48h], edx
0x14000b1b2  jnz     short loc_14000B1BC
0x14000b1b4  mov     [rsi], rdx
0x14000b1b7  mov     [r8], edx
0x14000b1ba  jmp     short loc_14000B223
0x14000b1bc  cmp     [rcx+50h], rdx
0x14000b1c0  jz      short loc_14000B237
0x14000b1c2  cmp     [rcx+4Ch], dl
0x14000b1c5  jnz     short loc_14000B1F5
0x14000b1c7  mov     rax, [rcx+58h]
0x14000b1cb  test    rax, rax
0x14000b1ce  jz      short loc_14000B1F5
0x14000b1d0  mov     rax, [rcx+58h]
0x14000b1d4  mov     ecx, [rax+0Ch]
0x14000b1d7  cmp     ecx, 1
0x14000b1da  jnz     short loc_14000B1F5
0x14000b1dc  mov     rax, [rbx+50h]
0x14000b1e0  mov     [rsi], rax
0x14000b1e3  mov     eax, [rbx+48h]
0x14000b1e6  mov     [r8], eax
0x14000b1e9  mov     [rbx+48h], edx
0x14000b1ec  mov     [rbx+4Ch], dl
0x14000b1ef  mov     [rbx+50h], rdx
0x14000b1f3  jmp     short loc_14000B223
0x14000b1f5  cmp     [rbx+4Ch], dl
0x14000b1f8  jnz     short loc_14000B20F
0x14000b1fa  mov     rax, [rbx+58h]
0x14000b1fe  test    rax, rax
0x14000b201  jz      short loc_14000B237
0x14000b203  mov     rax, [rbx+58h]
0x14000b207  mov     ecx, [rax+0Ch]
0x14000b20a  cmp     ecx, 1
0x14000b20d  jle     short loc_14000B237
0x14000b20f  mov     edx, [rbx+48h]
0x14000b212  mov     rcx, [rbx+50h]
0x14000b216  call    ?AllocateAndCopyElements@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@KAPEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@PEBV34567@I@Z; Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(Windows::UI::Xaml::Markup::XmlnsDefinition const *,uint)
0x14000b21b  mov     [rsi], rax
0x14000b21e  mov     eax, [rbx+48h]
0x14000b221  mov     [rdi], eax
0x14000b223  mov     rax, [rbx]
0x14000b226  mov     rcx, rbx
0x14000b229  mov     rax, [rax+10h]
0x14000b22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b232  jmp     loc_14000B18D
0x14000b237  call    cs:__imp_?__abi_WinRTraiseFailureException@@YAXXZ; __abi_WinRTraiseFailureException(void)
0x14000b23d  int     3; Trap to Debugger
0x14000b23e  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
```
