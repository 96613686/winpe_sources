# RealCloudPlayerMigXml(ushort * *,ushort const *,void *)

- ea: `0x180036ae0`
- end: `0x180036ba7`
- name: `?RealCloudPlayerMigXml@@YAJPEAPEAGPEBGPEAX@Z`
- size: `199`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a5e0`
- `0x180036ae0`
- `0x1800543c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180036b0a`
- `ntdll!RtlAllocateHeap` at `0x180036b0a`
- `ntdll!RtlFreeHeap` at `0x180036b8a`
- `ntdll!RtlFreeHeap` at `0x180036b8a`

## string_xrefs

- `0x180036b1d`: `Failed to allocate migxml buffer [%x]`
- `0x180036b61`: `Failed to copy migxml to buffer [%x]`
- `0x180036b3d`: `<component type="Application" context="UserAndSystem">   <displayName>Real Cloud Player Migration Data</displayName>  <role role="Settings">                                     <rules context="System">                                       <include>                                       <objectSet>                                                  	<pattern type="Registry">HKLM\SYSTEM\CURRENTCONTROLSET\SERVICES\REALPLAYERUPDATESVC [START]</pattern>     </objectSet>                                `
- `0x180036b2c`: `RealCloudPlayerMigXml`
- `0x180036b68`: `RealCloudPlayerMigXml`

## pseudocode

```c
__int64 __fastcall RealCloudPlayerMigXml(unsigned __int16 **a1, const unsigned __int16 *a2, void *a3)
{
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax

  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xD1Cu);
  v5 = Heap;
  if ( Heap )
  {
    v7 = StringCchCopyW(
           Heap,
           0x68Eu,
           L"<component type=\"Application\" context=\"UserAndSystem\">   <displayName>Real Cloud Player Migration Data</d"
            "isplayName>  <role role=\"Settings\">                                     <rules context=\"System\">        "
            "                               <include>                                       <objectSet>                  "
            "                                \t<pattern type=\"Registry\">HKLM\\SYSTEM\\CURRENTCONTROLSET\\SERVICES\\REAL"
            "PLAYERUPDATESVC [START]</pattern>     </objectSet>                                                          "
            "                                              </include>                                                    "
            "                                         <addObjects>                                                       "
            "                                           <object>                                                         "
            "                                                 <location type=\"Registry\">HKLM\\SYSTEM\\CURRENTCONTROLSET"
            "\\SERVICES\\REALPLAYERUPDATESVC [START]</location>           <attributes>DWORD</attributes>                 "
            "                                                               <bytes>00000004</bytes>                      "
            "                                                             </object>                                      "
            "                                                               </addObjects>                                "
            "                                                                 </rules>                                   "
            "                                                                 </role>                                    "
            "                                                                 </component>");
    v6 = v7;
    if ( v7 >= 0 )
    {
      *a1 = v5;
    }
    else
    {
      AslLogCallPrintf(1, "RealCloudPlayerMigXml", 96, "Failed to copy migxml to buffer [%x]", v7);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    }
  }
  else
  {
    v6 = -2147024882;
    AslLogCallPrintf(1, "RealCloudPlayerMigXml", 89, "Failed to allocate migxml buffer [%x]", -2147024882);
  }
  return v6;
}

```

## disassembly

```asm
0x180036ae0  mov     [rsp+arg_0], rbx
0x180036ae5  mov     [rsp+arg_8], rsi
0x180036aea  push    rdi
0x180036aeb  sub     rsp, 30h
0x180036aef  mov     rsi, rcx
0x180036af2  mov     edx, 8; Flags
0x180036af7  mov     rcx, gs:60h
0x180036b00  mov     r8d, 0D1Ch; Size
0x180036b06  mov     rcx, [rcx+30h]; HeapHandle
0x180036b0a  call    cs:__imp_RtlAllocateHeap
0x180036b10  mov     rdi, rax
0x180036b13  test    rax, rax
0x180036b16  jnz     short loc_180036B3D
0x180036b18  mov     ebx, 8007000Eh
0x180036b1d  lea     r9, aFailedToAlloca_14; "Failed to allocate migxml buffer [%x]"
0x180036b24  lea     r8d, [rax+59h]
0x180036b28  mov     [rsp+38h+var_18], ebx
0x180036b2c  lea     rdx, aRealcloudplaye_2; "RealCloudPlayerMigXml"
0x180036b33  lea     ecx, [rax+1]
0x180036b36  call    AslLogCallPrintf
0x180036b3b  jmp     short loc_180036B95
0x180036b3d  lea     r8, aComponentTypeA_1; "<component type=\"Application\" context"...
0x180036b44  mov     edx, 68Eh; unsigned __int64
0x180036b49  mov     rcx, rdi; unsigned __int16 *
0x180036b4c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036b51  mov     ebx, eax
0x180036b53  test    eax, eax
0x180036b55  jns     short loc_180036B92
0x180036b57  mov     r8d, 60h ; '`'
0x180036b5d  mov     [rsp+38h+var_18], eax
0x180036b61  lea     r9, aFailedToCopyMi; "Failed to copy migxml to buffer [%x]"
0x180036b68  lea     rdx, aRealcloudplaye_2; "RealCloudPlayerMigXml"
0x180036b6f  lea     ecx, [r8-5Fh]
0x180036b73  call    AslLogCallPrintf
0x180036b78  mov     rcx, gs:60h
0x180036b81  mov     r8, rdi; P
0x180036b84  xor     edx, edx; Flags
0x180036b86  mov     rcx, [rcx+30h]; HeapHandle
0x180036b8a  call    cs:__imp_RtlFreeHeap
0x180036b90  jmp     short loc_180036B95
0x180036b92  mov     [rsi], rdi
0x180036b95  mov     rsi, [rsp+38h+arg_8]
0x180036b9a  mov     eax, ebx
0x180036b9c  mov     rbx, [rsp+38h+arg_0]
0x180036ba1  add     rsp, 30h
0x180036ba5  pop     rdi
0x180036ba6  retn
```
