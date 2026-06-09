# ProviderSubSystem_Globals::Initialize_Events(void)

- ea: `0x1400242f8`
- end: `0x140024402`
- name: `?Initialize_Events@ProviderSubSystem_Globals@@SAJXZ`
- size: `266`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x1400234b8`
- `0x1400242f8`

## import_xrefs

- `NCObjAPI!WmiEventSourceConnect` at `0x14002433a`
- `NCObjAPI!WmiEventSourceConnect` at `0x14002433a`
- `NCObjAPI!WmiCreateObjectWithFormat` at `0x1400243bd`
- `NCObjAPI!WmiCreateObjectWithFormat` at `0x1400243bd`
- `wbemcomn!GetMemLogObject` at `0x140024354`
- `wbemcomn!GetMemLogObject` at `0x140024354`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002435f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002435f`

## pseudocode

```c
__int64 ProviderSubSystem_Globals::Initialize_Events(void)
{
  void *v0; // rcx
  unsigned int v1; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 i; // rdi
  void **ObjectWithFormat; // rax

  ProviderSubSystem_Globals::s_EventSource = (void *)WmiEventSourceConnect(
                                                       L"root\\cimv2",
                                                       L"ProviderSubSystem",
                                                       1,
                                                       32000,
                                                       100,
                                                       0,
                                                       0);
  v0 = ProviderSubSystem_Globals::s_EventSource;
  if ( ProviderSubSystem_Globals::s_EventSource )
  {
    v1 = 0;
    for ( i = 0; (unsigned int)i < 0x23; i = (unsigned int)(i + 1) )
    {
      ObjectWithFormat = (void **)WmiCreateObjectWithFormat(
                                    v0,
                                    (&ProviderSubSystem_Globals::s_EventPropertySources)[(unsigned int)(2 * i)],
                                    1,
                                    (&ProviderSubSystem_Globals::s_EventPropertySources)[(unsigned int)(2 * i + 1)]);
      (&ProviderSubSystem_Globals::s_EventClassHandles)[i] = ObjectWithFormat;
      if ( !ObjectWithFormat )
        goto LABEL_2;
      v0 = ProviderSubSystem_Globals::s_EventSource;
    }
  }
  else
  {
LABEL_2:
    v1 = -2147217398;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217398);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x1400242f8  mov     rax, rsp
0x1400242fb  mov     [rax+8], rbx
0x1400242ff  mov     [rax+10h], rdi
0x140024303  push    r14
0x140024305  sub     rsp, 40h
0x140024309  mov     qword ptr [rax-18h], 0
0x140024311  lea     rdx, aProvidersubsys; "ProviderSubSystem"
0x140024318  mov     qword ptr [rax-20h], 0
0x140024320  lea     rcx, aRootCimv2; "root\\cimv2"
0x140024327  mov     r9d, 7D00h
0x14002432d  mov     dword ptr [rax-28h], 64h ; 'd'
0x140024334  mov     r8d, 1
0x14002433a  call    cs:__imp_WmiEventSourceConnect
0x140024340  mov     cs:?s_EventSource@ProviderSubSystem_Globals@@2PEAXEA, rax; void * ProviderSubSystem_Globals::s_EventSource
0x140024347  mov     rcx, rax
0x14002434a  test    rax, rax
0x14002434d  jnz     short loc_140024391
0x14002434f  mov     ebx, 8004100Ah
0x140024354  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002435a  mov     rcx, rax
0x14002435d  mov     edx, ebx
0x14002435f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140024365  mov     rcx, cs:WPP_GLOBAL_Control
0x14002436c  lea     rax, WPP_GLOBAL_Control
0x140024373  cmp     rcx, rax
0x140024376  jz      short loc_14002437E
0x140024378  test    byte ptr [rcx+1Ch], 4
0x14002437c  jnz     short loc_1400243DF
0x14002437e  mov     rdi, [rsp+48h+arg_8]
0x140024383  mov     eax, ebx
0x140024385  mov     rbx, [rsp+48h+arg_0]
0x14002438a  add     rsp, 40h
0x14002438e  pop     r14
0x140024390  retn
0x140024391  xor     ebx, ebx
0x140024393  lea     r14, __ImageBase
0x14002439a  xor     edi, edi
0x14002439c  cmp     edi, 23h ; '#'
0x14002439f  jnb     short loc_140024365
0x1400243a1  lea     edx, [rdi+rdi]
0x1400243a4  mov     r8d, 1
0x1400243aa  lea     eax, [rdx+1]
0x1400243ad  mov     rdx, ds:rva ?s_EventPropertySources@ProviderSubSystem_Globals@@2PAPEAGA[r14+rdx*8]; ushort * near * ProviderSubSystem_Globals::s_EventPropertySources ...
0x1400243b5  mov     r9, ds:rva ?s_EventPropertySources@ProviderSubSystem_Globals@@2PAPEAGA[r14+rax*8]; ushort * near * ProviderSubSystem_Globals::s_EventPropertySources ...
0x1400243bd  call    cs:__imp_WmiCreateObjectWithFormat
0x1400243c3  mov     rva ?s_EventClassHandles@ProviderSubSystem_Globals@@2PAPEAXA[r14+rdi*8], rax; void * near * ProviderSubSystem_Globals::s_EventClassHandles ...
0x1400243cb  test    rax, rax
0x1400243ce  jz      loc_14002434F
0x1400243d4  mov     rcx, cs:?s_EventSource@ProviderSubSystem_Globals@@2PEAXEA; void * ProviderSubSystem_Globals::s_EventSource
0x1400243db  inc     edi
0x1400243dd  jmp     short loc_14002439C
0x1400243df  cmp     byte ptr [rcx+19h], 2
0x1400243e3  jb      short loc_14002437E
0x1400243e5  mov     rcx, [rcx+10h]
0x1400243e9  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x1400243f0  mov     edx, 0Ah
0x1400243f5  mov     r9d, ebx
0x1400243f8  call    WPP_SF_d
0x1400243fd  jmp     loc_14002437E
```
