# MigrateVCRuntimeEmptyMigXml(ushort * *,ushort const *,void *)

- ea: `0x180036470`
- end: `0x18003653a`
- name: `?MigrateVCRuntimeEmptyMigXml@@YAJPEAPEAGPEBGPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a5e0`
- `0x180036470`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003649a`
- `ntdll!RtlAllocateHeap` at `0x18003649a`
- `ntdll!RtlFreeHeap` at `0x18003651d`
- `ntdll!RtlFreeHeap` at `0x18003651d`

## string_xrefs

- `0x1800364cf`: `<component type="Application" context="UserAndSystem">                                                                                                  <displayName>Empty Migration Data-{772A6680-74F3-478F-AD22-3909187540FD}</displayName>                                                                      <role role="Settings">                                                                                                                                    <rules context = "System">            `
- `0x1800364ad`: `[MigrateVCRuntimeShim] Failed to allocate migxml buffer [%x]`
- `0x1800364be`: `MigrateVCRuntimeEmptyMigXml`
- `0x1800364fa`: `MigrateVCRuntimeEmptyMigXml`
- `0x1800364e9`: `[MigrateVCRuntimeShim] Failed to copy migxml to buffer [%x]`

## pseudocode

```c
__int64 __fastcall MigrateVCRuntimeEmptyMigXml(unsigned __int16 **a1, const unsigned __int16 *a2, void *a3)
{
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax

  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xD0Eu);
  v5 = Heap;
  if ( Heap )
  {
    v7 = StringCchCopyW(
           Heap,
           0x687u,
           L"<component type=\"Application\" context=\"UserAndSystem\">                                                   "
            "                                               <displayName>Empty Migration Data-{772A6680-74F3-478F-AD22-39"
            "09187540FD}</displayName>                                                                      <role role=\""
            "Settings\">                                                                                                 "
            "                                   <rules context = \"System\">                                             "
            "                                                                                   <unconditionalExclude>   "
            "                                                                                                            "
            "                       <objectSet>                                                                          "
            "                                                                       <pattern type =\"Registry\">HKLM\\SYS"
            "TEM\\CURRENTCONTROLSET\\SERVICES\\{772A6680-74F3-478F-AD22-3909187540FD} [EMPTY]</pattern>                  "
            "   </objectSet>                                                                                             "
            "                                           </unconditionalExclude>                                          "
            "                                                                                   </rules>                 "
            "                                                                                                            "
            "               </role>                                                                                      "
            "                                                   </component>");
    v6 = v7;
    if ( v7 >= 0 )
    {
      *a1 = v5;
    }
    else
    {
      AslLogCallPrintf(
        1,
        "MigrateVCRuntimeEmptyMigXml",
        161,
        "[MigrateVCRuntimeShim] Failed to copy migxml to buffer [%x]",
        v7);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
  }
  else
  {
    v6 = -2147024882;
    AslLogCallPrintf(
      1,
      "MigrateVCRuntimeEmptyMigXml",
      154,
      "[MigrateVCRuntimeShim] Failed to allocate migxml buffer [%x]",
      -2147024882);
  }
  return v6;
}

```

## disassembly

```asm
0x180036470  mov     [rsp+arg_0], rbx
0x180036475  mov     [rsp+arg_8], rsi
0x18003647a  push    rdi
0x18003647b  sub     rsp, 30h
0x18003647f  mov     rsi, rcx
0x180036482  mov     edx, 8; Flags
0x180036487  mov     rcx, gs:60h
0x180036490  mov     r8d, 0D0Eh; Size
0x180036496  mov     rcx, [rcx+30h]; HeapHandle
0x18003649a  call    cs:__imp_RtlAllocateHeap
0x1800364a0  mov     rdi, rax
0x1800364a3  test    rax, rax
0x1800364a6  jnz     short loc_1800364CF
0x1800364a8  mov     ebx, 8007000Eh
0x1800364ad  lea     r9, aMigratevcrunti_3; "[MigrateVCRuntimeShim] Failed to alloca"...
0x1800364b4  mov     r8d, 9Ah
0x1800364ba  mov     [rsp+38h+var_18], ebx
0x1800364be  lea     rdx, aMigratevcrunti_5; "MigrateVCRuntimeEmptyMigXml"
0x1800364c5  lea     ecx, [rax+1]
0x1800364c8  call    AslLogCallPrintf
0x1800364cd  jmp     short loc_180036528
0x1800364cf  lea     r8, aComponentTypeA_0; "<component type=\"Application\" context"...
0x1800364d6  mov     edx, 687h; unsigned __int64
0x1800364db  mov     rcx, rdi; unsigned __int16 *
0x1800364de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800364e3  mov     ebx, eax
0x1800364e5  test    eax, eax
0x1800364e7  jns     short loc_180036525
0x1800364e9  lea     r9, aMigratevcrunti_0; "[MigrateVCRuntimeShim] Failed to copy m"...
0x1800364f0  mov     [rsp+38h+var_18], eax
0x1800364f4  mov     r8d, 0A1h
0x1800364fa  lea     rdx, aMigratevcrunti_5; "MigrateVCRuntimeEmptyMigXml"
0x180036501  mov     ecx, 1
0x180036506  call    AslLogCallPrintf
0x18003650b  mov     rcx, gs:60h
0x180036514  mov     r8, rdi; P
0x180036517  xor     edx, edx; Flags
0x180036519  mov     rcx, [rcx+30h]; HeapHandle
0x18003651d  call    cs:__imp_RtlFreeHeap
0x180036523  jmp     short loc_180036528
0x180036525  mov     [rsi], rdi
0x180036528  mov     rsi, [rsp+38h+arg_8]
0x18003652d  mov     eax, ebx
0x18003652f  mov     rbx, [rsp+38h+arg_0]
0x180036534  add     rsp, 30h
0x180036538  pop     rdi
0x180036539  retn
```
