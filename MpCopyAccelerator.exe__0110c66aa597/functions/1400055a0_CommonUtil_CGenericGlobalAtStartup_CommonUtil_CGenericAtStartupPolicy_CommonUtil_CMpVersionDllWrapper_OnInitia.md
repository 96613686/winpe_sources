# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x1400055a0`
- end: `0x1400055e1`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b3c`
- `0x1400055a0`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(
        __int64 a1,
        __int64 a2,
        void *a3)
{
  __int64 v3; // rbx
  __int64 result; // rax

  v3 = a1 - 8;
  if ( *(_BYTE *)(a1 - 8 + 40) )
    return 2147942487LL;
  *(_BYTE *)(v3 + 40) = 1;
  result = CommonUtil::OnInitializeAtStartupNoThrow(
             (CommonUtil *)CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitializeCallback,
             (int (*)(void *))(a1 - 8),
             a3);
  if ( (int)result >= 0 )
    return 0;
  *(_BYTE *)(v3 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x1400055a0  push    rbx
0x1400055a2  sub     rsp, 20h
0x1400055a6  lea     rbx, [rcx-8]
0x1400055aa  cmp     byte ptr [rbx+28h], 0
0x1400055ae  jz      short loc_1400055B7
0x1400055b0  mov     eax, 80070057h
0x1400055b5  jmp     short loc_1400055DB
0x1400055b7  mov     rdx, rbx; int (*)(void *)
0x1400055ba  mov     byte ptr [rbx+28h], 1
0x1400055be  lea     rcx, ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; this
0x1400055c5  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x1400055ca  mov     ecx, eax
0x1400055cc  shr     ecx, 1Fh
0x1400055cf  test    cl, cl
0x1400055d1  jz      short loc_1400055D9
0x1400055d3  mov     byte ptr [rbx+28h], 0
0x1400055d7  jmp     short loc_1400055DB
0x1400055d9  xor     eax, eax
0x1400055db  add     rsp, 20h
0x1400055df  pop     rbx
0x1400055e0  retn
```
