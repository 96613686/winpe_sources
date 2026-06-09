# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)

- ea: `0x180008a30`
- end: `0x180008a65`
- name: `?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy@VCMpVersionDllWrapper@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008a30`
- `0x180008e98`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy<CommonUtil::CMpVersionDllWrapper>>::OnInitialize(
        CommonUtil *a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  char *v3; // rbx
  __int64 result; // rax

  v3 = (char *)a1 - 8;
  if ( *((_BYTE *)a1 + 32) )
    return 2147942487LL;
  v3[40] = 1;
  result = CommonUtil::OnInitializeAtStartupNoThrow(a1, (HMODULE *)a1 - 1, a3);
  if ( (int)result >= 0 )
    return 0;
  v3[40] = 0;
  return result;
}

```

## disassembly

```asm
0x180008a30  push    rbx
0x180008a32  sub     rsp, 20h
0x180008a36  lea     rbx, [rcx-8]
0x180008a3a  cmp     byte ptr [rbx+28h], 0
0x180008a3e  jz      short loc_180008A47
0x180008a40  mov     eax, 80070057h
0x180008a45  jmp     short loc_180008A5F
0x180008a47  mov     rdx, rbx; int (*)(void *)
0x180008a4a  mov     byte ptr [rbx+28h], 1
0x180008a4e  call    ?OnInitializeAtStartupNoThrow@CommonUtil@@YAJP6AJPEAX@Z0@Z; CommonUtil::OnInitializeAtStartupNoThrow(long (*)(void *),void *)
0x180008a53  test    eax, eax
0x180008a55  jns     short loc_180008A5D
0x180008a57  mov     byte ptr [rbx+28h], 0
0x180008a5b  jmp     short loc_180008A5F
0x180008a5d  xor     eax, eax
0x180008a5f  add     rsp, 20h
0x180008a63  pop     rbx
0x180008a64  retn
```
