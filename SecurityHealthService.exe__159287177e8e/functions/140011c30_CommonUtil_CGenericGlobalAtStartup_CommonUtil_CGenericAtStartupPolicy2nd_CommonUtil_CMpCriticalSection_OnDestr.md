# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x140011c30`
- end: `0x140011c6c`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011c50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011c50`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy(
        __int64 a1)
{
  __int64 v1; // rbx
  bool v2; // zf
  __int64 result; // rax

  v1 = a1 - 40;
  if ( *(_BYTE *)(a1 - 40 + 72) )
  {
    v2 = *(_DWORD *)(v1 + 12) == 252844334;
    *(_BYTE *)(v1 + 72) = 0;
    if ( !v2 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
    result = 0;
    *(_OWORD *)v1 = 0;
    *(_OWORD *)(v1 + 16) = 0;
    *(_QWORD *)(v1 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140011c30  push    rbx
0x140011c32  sub     rsp, 20h
0x140011c36  lea     rbx, [rcx-28h]
0x140011c3a  cmp     byte ptr [rbx+48h], 0
0x140011c3e  jz      short loc_140011C66
0x140011c40  cmp     dword ptr [rbx+0Ch], 0F12192Eh
0x140011c47  mov     byte ptr [rbx+48h], 0
0x140011c4b  jz      short loc_140011C56
0x140011c4d  mov     rcx, rbx; lpCriticalSection
0x140011c50  call    cs:__imp_DeleteCriticalSection
0x140011c56  xorps   xmm0, xmm0
0x140011c59  xor     eax, eax
0x140011c5b  movups  xmmword ptr [rbx], xmm0
0x140011c5e  movups  xmmword ptr [rbx+10h], xmm0
0x140011c62  mov     [rbx+20h], rax
0x140011c66  add     rsp, 20h
0x140011c6a  pop     rbx
0x140011c6b  retn
```
