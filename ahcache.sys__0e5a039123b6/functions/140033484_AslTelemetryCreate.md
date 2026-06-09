# AslTelemetryCreate

- ea: `0x140033484`
- end: `0x1400335cb`
- name: `AslTelemetryCreate`
- size: `327`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140028fec`

## callees

- `0x14000436d`
- `0x140004391`
- `0x140006484`
- `0x1400321ac`
- `0x140033484`
- `0x1400335d4`
- `0x140033ec0`
- `0x14003e364`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!strcpy_s` at `0x140033525`
- `ntoskrnl!strcpy_s` at `0x140033525`

## string_xrefs

- `0x1400334f5`: `ahcache`
- `0x1400334c9`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  int v3; // edi
  void *v4; // rcx

  if ( _InterlockedIncrement(&dword_14001E778) == 1 )
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  v1 = AslAlloc(a1, 312, 0);
  v2 = v1;
  if ( v1 )
  {
    ExInitializeResourceLite_0((PERESOURCE)(v1 + 88));
    *(_QWORD *)(v2 + 288) = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
    strcpy_s((char *)v2, 0x40u, "ahcache");
    v3 = AslAnsiStringCreate((PANSI_STRING)(v2 + 72));
    if ( v3 < 0 || (v3 = RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(v2 + 192), v3 < 0) )
    {
      AslTelemetryDelete(v2);
    }
    else
    {
      v4 = *(void **)(v2 + 280);
      if ( v4 )
        ExFreePoolWithTag_0(v4, 0x72615452u);
      *(_QWORD *)(v2 + 240) = 0;
      v3 = 0;
      *(_QWORD *)(v2 + 272) = 4;
      *(_QWORD *)(v2 + 256) = 0;
      *(_QWORD *)(v2 + 264) = 0;
      *(_QWORD *)(v2 + 280) = 0;
      *(_QWORD *)(v2 + 248) = 48;
      qword_14001E670 = v2;
    }
  }
  else
  {
    v3 = -1073741801;
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140033484  mov     [rsp+arg_0], rbx
0x140033489  push    rdi
0x14003348a  sub     rsp, 30h
0x14003348e  mov     eax, 1
0x140033493  lock xadd cs:dword_14001E778, eax
0x14003349b  inc     eax
0x14003349d  cmp     eax, 1
0x1400334a0  jnz     short loc_1400334A7
0x1400334a2  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400334a7  xor     r8d, r8d
0x1400334aa  mov     edx, 138h
0x1400334af  call    AslAlloc
0x1400334b4  mov     rbx, rax
0x1400334b7  test    rax, rax
0x1400334ba  jnz     short loc_1400334E2
0x1400334bc  lea     r9, aOutOfMemory; "Out of memory"
0x1400334c3  mov     r8d, 0CCh
0x1400334c9  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x1400334d0  mov     edi, 0C0000017h
0x1400334d5  lea     ecx, [rax+1]
0x1400334d8  call    AslLogCallPrintf
0x1400334dd  jmp     loc_1400335BD
0x1400334e2  lea     rcx, [rax+58h]; Resource
0x1400334e6  call    ExInitializeResourceLite_0
0x1400334eb  mov     rax, 0FFFFF78000000004h
0x1400334f5  lea     r8, aAhcache; "ahcache"
0x1400334fc  mov     ecx, [rax]
0x1400334fe  mov     rax, 0FFFFF78000000320h
0x140033508  shl     rcx, 20h
0x14003350c  mov     rax, [rax]
0x14003350f  shl     rax, 8
0x140033513  mul     rcx
0x140033516  mov     rcx, rbx; char *
0x140033519  mov     [rbx+120h], rdx
0x140033520  mov     edx, 40h ; '@'; SizeInBytes
0x140033525  call    cs:__imp_strcpy_s
0x14003352c  nop     dword ptr [rax+rax+00h]
0x140033531  lea     rcx, [rbx+48h]; DestinationString
0x140033535  call    AslAnsiStringCreate
0x14003353a  mov     edi, eax
0x14003353c  test    eax, eax
0x14003353e  js      short loc_1400335B5
0x140033540  lea     rcx, [rbx+0C0h]
0x140033547  call    ?Initialize@?$RtlArray@U_ASL_TELEMETRY_EVENT@@@@QEAAJPEAX_K1H@Z; RtlArray<_ASL_TELEMETRY_EVENT>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x14003354c  mov     edi, eax
0x14003354e  test    eax, eax
0x140033550  js      short loc_1400335B5
0x140033552  mov     rcx, [rbx+118h]; P
0x140033559  test    rcx, rcx
0x14003355c  jz      short loc_140033568
0x14003355e  mov     edx, 72615452h; Tag
0x140033563  call    ExFreePoolWithTag_0
0x140033568  mov     qword ptr [rbx+0F0h], 0
0x140033573  xor     edi, edi
0x140033575  mov     qword ptr [rbx+110h], 4
0x140033580  mov     qword ptr [rbx+100h], 0
0x14003358b  mov     qword ptr [rbx+108h], 0
0x140033596  mov     qword ptr [rbx+118h], 0
0x1400335a1  mov     qword ptr [rbx+0F8h], 30h ; '0'
0x1400335ac  mov     cs:qword_14001E670, rbx
0x1400335b3  jmp     short loc_1400335BD
0x1400335b5  mov     rcx, rbx
0x1400335b8  call    AslTelemetryDelete
0x1400335bd  mov     rbx, [rsp+38h+arg_0]
0x1400335c2  mov     eax, edi
0x1400335c4  add     rsp, 30h
0x1400335c8  pop     rdi
0x1400335c9  retn
```
