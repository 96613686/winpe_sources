# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)

- ea: `0x14000f800`
- end: `0x14000f83c`
- name: `?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000f800`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000f820`
- `KERNEL32!DeleteCriticalSection` at `0x14000f820`

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
0x14000f800  push    rbx
0x14000f802  sub     rsp, 20h
0x14000f806  lea     rbx, [rcx-28h]
0x14000f80a  cmp     byte ptr [rbx+48h], 0
0x14000f80e  jz      short loc_14000F836
0x14000f810  cmp     dword ptr [rbx+0Ch], 0F12192Eh
0x14000f817  mov     byte ptr [rbx+48h], 0
0x14000f81b  jz      short loc_14000F826
0x14000f81d  mov     rcx, rbx; lpCriticalSection
0x14000f820  call    cs:__imp_DeleteCriticalSection
0x14000f826  xorps   xmm0, xmm0
0x14000f829  xor     eax, eax
0x14000f82b  movups  xmmword ptr [rbx], xmm0
0x14000f82e  movups  xmmword ptr [rbx+10h], xmm0
0x14000f832  mov     [rbx+20h], rax
0x14000f836  add     rsp, 20h
0x14000f83a  pop     rbx
0x14000f83b  retn
```
