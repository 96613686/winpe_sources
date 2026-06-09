# RemoveDataFromIndex(_INDEX_STRUCT *,NDX_OBJREF *)

- ea: `0x18000b244`
- end: `0x18000b31b`
- name: `?RemoveDataFromIndex@@YAXPEAU_INDEX_STRUCT@@PEAUNDX_OBJREF@@@Z`
- size: `215`
- prototype: `void __fastcall(struct _INDEX_STRUCT *, struct NDX_OBJREF *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b3fc`
- `0x180011df0`

## callees

- `0x180003514`
- `0x180007f3c`
- `0x18000b02c`
- `0x18000b244`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000b2f7`
- `KERNEL32!GetProcessHeap` at `0x18000b2f7`
- `KERNEL32!HeapFree` at `0x18000b305`
- `KERNEL32!HeapFree` at `0x18000b305`
- `DEVRTL!NdxTableRemoveObject` at `0x18000b2d6`
- `DEVRTL!NdxTableRemoveObject` at `0x18000b2d6`
- `DEVRTL!NdxTableGetPropertyValue` at `0x18000b2a6`
- `DEVRTL!NdxTableGetPropertyValue` at `0x18000b2a6`

## pseudocode

```c
void __fastcall RemoveDataFromIndex(struct _INDEX_STRUCT *a1, struct NDX_OBJREF *a2)
{
  WCHAR *v2; // rbx
  const WCHAR *ObjectString; // rax
  __int64 v6; // rdx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v8 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  RemoveDataFromIdMap(a1, a2);
  if ( (unsigned int)NdxTableGetPropertyValue(a2, 1, &v8) )
  {
    if ( v8 )
    {
      ObjectString = MemGetObjectString(a2, 2);
      v2 = (WCHAR *)ObjectString;
      if ( ObjectString )
        FSRemoveDirPath(ObjectString);
    }
  }
  NdxTableRemoveObject(a2);
  if ( !g_nPackages )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v6);
  _InterlockedDecrement(&g_nPackages);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x18000b244  mov     [rsp+arg_8], rbx
0x18000b249  mov     [rsp+arg_10], rsi
0x18000b24e  push    rdi
0x18000b24f  sub     rsp, 30h
0x18000b253  xor     ebx, ebx
0x18000b255  mov     [rsp+38h+arg_0], 0
0x18000b25d  mov     rdi, rdx
0x18000b260  mov     rsi, rcx
0x18000b263  test    rcx, rcx
0x18000b266  jnz     short loc_18000B26D
0x18000b268  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b26d  cmp     dword ptr [rsi], 494E4445h
0x18000b273  jz      short loc_18000B27A
0x18000b275  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b27a  test    rdi, rdi
0x18000b27d  jnz     short loc_18000B284
0x18000b27f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b284  mov     rdx, rdi
0x18000b287  mov     rcx, rsi
0x18000b28a  call    RemoveDataFromIdMap
0x18000b28f  mov     r9d, 4
0x18000b295  mov     [rsp+38h+var_18], rbx
0x18000b29a  lea     r8, [rsp+38h+arg_0]
0x18000b29f  mov     rcx, rdi
0x18000b2a2  lea     edx, [r9-3]
0x18000b2a6  call    cs:__imp_NdxTableGetPropertyValue
0x18000b2ac  test    eax, eax
0x18000b2ae  jz      short loc_18000B2D3
0x18000b2b0  cmp     [rsp+38h+arg_0], ebx
0x18000b2b4  jz      short loc_18000B2D3
0x18000b2b6  mov     edx, 2; int
0x18000b2bb  mov     rcx, rdi; struct NDX_OBJREF *
0x18000b2be  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x18000b2c3  mov     rbx, rax
0x18000b2c6  test    rax, rax
0x18000b2c9  jz      short loc_18000B2D3
0x18000b2cb  mov     rcx, rax
0x18000b2ce  call    FSRemoveDirPath
0x18000b2d3  mov     rcx, rdi
0x18000b2d6  call    cs:__imp_NdxTableRemoveObject
0x18000b2dc  mov     ecx, cs:?g_nPackages@@3JC; long volatile g_nPackages
0x18000b2e2  test    ecx, ecx
0x18000b2e4  jnz     short loc_18000B2EB
0x18000b2e6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b2eb  lock dec cs:?g_nPackages@@3JC; long volatile g_nPackages
0x18000b2f2  test    rbx, rbx
0x18000b2f5  jz      short loc_18000B30B
0x18000b2f7  call    cs:__imp_GetProcessHeap
0x18000b2fd  mov     r8, rbx; lpMem
0x18000b300  xor     edx, edx; dwFlags
0x18000b302  mov     rcx, rax; hHeap
0x18000b305  call    cs:__imp_HeapFree
0x18000b30b  mov     rbx, [rsp+38h+arg_8]
0x18000b310  mov     rsi, [rsp+38h+arg_10]
0x18000b315  add     rsp, 30h
0x18000b319  pop     rdi
0x18000b31a  retn
```
