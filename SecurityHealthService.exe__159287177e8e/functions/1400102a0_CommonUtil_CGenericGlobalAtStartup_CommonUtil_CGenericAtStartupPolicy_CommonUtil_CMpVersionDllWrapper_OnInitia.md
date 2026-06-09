# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x1400102a0`
- end: `0x1400102dc`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400102a0`
- `0x140010f04`

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
0x1400102a0  push    rbx
0x1400102a2  sub     rsp, 20h
0x1400102a6  lea     rbx, [rcx-8]
0x1400102aa  cmp     byte ptr [rbx+28h], 0
0x1400102ae  jz      short loc_1400102B7
0x1400102b0  mov     eax, 80070057h
0x1400102b5  jmp     short loc_1400102D6
0x1400102b7  mov     rdx, rbx; int (*)(void *)
0x1400102ba  mov     byte ptr [rbx+28h], 1
0x1400102be  lea     rcx, ?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z; this
0x1400102c5  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x1400102ca  test    eax, eax
0x1400102cc  jns     short loc_1400102D4
0x1400102ce  mov     byte ptr [rbx+28h], 0
0x1400102d2  jmp     short loc_1400102D6
0x1400102d4  xor     eax, eax
0x1400102d6  add     rsp, 20h
0x1400102da  pop     rbx
0x1400102db  retn
```
