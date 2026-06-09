# KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)

- ea: `0x180015660`
- end: `0x1800157ba`
- name: `??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z`
- size: `346`
- prototype: `KspFunctionLogger *__fastcall(KspFunctionLogger *__hidden this, const unsigned __int16 *const, const int *)`
- caller_count: `124`
- callee_count: `3`
- tags: ``

## callers

- `0x180002094`
- `0x18000f880`
- `0x180011c60`
- `0x1800138e0`
- `0x1800159f0`
- `0x180018e20`
- `0x180019ed4`
- `0x18001b298`
- `0x18001b4a0`
- `0x18001bb00`
- `0x18001d590`
- `0x180021310`
- `0x1800222b4`
- `0x1800223c0`
- `0x180023894`
- `0x180029a80`
- `0x180029f48`
- `0x18002a634`
- `0x18002c3b0`
- `0x1800357ec`
- `0x180036f88`
- `0x18003ae74`
- `0x18003ce0c`
- `0x180046fe8`
- `0x180047cc0`
- `0x180048094`
- `0x180051618`
- `0x180053080`
- `0x1800536b0`
- `0x180055218`
- `0x180058948`
- `0x180058dec`
- `0x180059b78`
- `0x18005ac48`
- `0x18005aebc`
- `0x18005c2c0`
- `0x18005c400`
- `0x180066020`
- `0x18006c5c0`
- `0x18006dd40`
- `0x18006ddd0`
- `0x18006e000`
- `0x18006e0a0`
- `0x18006e1e0`
- `0x18006e290`
- `0x18006e370`
- `0x18006e660`
- `0x18006ec00`
- `0x18006ec90`
- `0x18006ff10`

## callees

- `0x180015660`
- `0x18003cf80`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015791`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015791`

## pseudocode

```c
KspFunctionLogger *__fastcall KspFunctionLogger::KspFunctionLogger(
        KspFunctionLogger *this,
        const unsigned __int16 *const a2,
        const int *a3)
{
  __int64 v4; // r10
  int *v5; // rcx
  __int64 v6; // rax
  int v8; // eax
  __int64 v10; // [rsp+38h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+6Ch] [rbp-3Ch]
  __int64 *v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  int *v18; // [rsp+80h] [rbp-28h]
  int v19; // [rsp+88h] [rbp-20h]
  int v20; // [rsp+8Ch] [rbp-1Ch]

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = a3;
  *((_BYTE *)this + 16) = 0;
  v4 = *((_QWORD *)KspDebugProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u )
  {
    v5 = *(int **)this;
    v10 = 0x1000000;
    if ( v5 )
    {
      v6 = -1;
      while ( *((_WORD *)v5 + ++v6) != 0 )
        ;
      v8 = 2 * v6 + 2;
    }
    else
    {
      v5 = &dword_1800DB714;
      v8 = 2;
    }
    v19 = v8;
    v18 = v5;
    v16 = &v10;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v4 + 8);
    v20 = 0;
    EventDescriptor.Keyword = 0;
    v17 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v13 = qword_1800F9F48;
    UserData.Reserved = 2;
    v14 = 37;
    v15 = 1;
    EventWriteTransfer(*(_QWORD *)(v4 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return this;
}

```

## disassembly

```asm
0x180015660  push    rbx
0x180015662  sub     rsp, 0A0h
0x180015669  mov     rax, cs:__security_cookie
0x180015670  xor     rax, rsp
0x180015673  mov     [rsp+0A8h+var_18], rax
0x18001567b  mov     rbx, rcx
0x18001567e  mov     [rcx], rdx
0x180015681  mov     [rcx+8], r8
0x180015685  mov     byte ptr [rcx+10h], 0
0x180015689  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x18001568e  mov     r10, [rax+8]
0x180015692  mov     eax, [r10]
0x180015695  cmp     eax, 5
0x180015698  jbe     loc_18001579D
0x18001569e  mov     rcx, [rbx]
0x1800156a1  mov     [rsp+0A8h+var_70], 1000000h
0x1800156aa  test    rcx, rcx
0x1800156ad  jz      short loc_1800156D5
0x1800156af  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800156b6  nop     word ptr [rax+rax+00000000h]
0x1800156c0  cmp     word ptr [rcx+rax*2+2], 0
0x1800156c6  lea     rax, [rax+1]
0x1800156ca  jnz     short loc_1800156C0
0x1800156cc  lea     eax, ds:2[rax*2]
0x1800156d3  jmp     short loc_1800156E1
0x1800156d5  lea     rcx, dword_1800DB714
0x1800156dc  mov     eax, 2
0x1800156e1  mov     [rsp+0A8h+var_20], eax
0x1800156e8  lea     rdx, _TraceLoggingMetadataEnd
0x1800156ef  mov     [rsp+0A8h+var_28], rcx
0x1800156f7  lea     rax, [rsp+0A8h+var_70]
0x1800156fc  mov     [rsp+0A8h+var_38], rax
0x180015701  xor     ecx, ecx
0x180015703  movzx   eax, cs:word_1800F9F3E
0x18001570a  xor     r9d, r9d; RelatedActivityId
0x18001570d  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x180015711  xor     r8d, r8d; ActivityId
0x180015714  mov     rax, [r10+8]
0x180015718  mov     [rsp+0A8h+var_58.Ptr], rax
0x18001571d  mov     [rsp+0A8h+var_1C], ecx
0x180015724  mov     [rsp+0A8h+EventDescriptor.Keyword], rcx
0x180015729  mov     [rsp+0A8h+var_30], 8
0x180015732  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x18001573a  movzx   eax, word ptr [rax]
0x18001573d  mov     [rsp+0A8h+var_58.Size], eax
0x180015741  lea     rax, qword_1800F9F48
0x180015748  mov     [rsp+0A8h+var_48], rax
0x18001574d  lea     rax, _TraceLoggingMetadata
0x180015754  sub     edx, eax
0x180015756  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x18001575e  mov     [rsp+0A8h+var_40], 25h ; '%'
0x180015766  lea     rax, [rsp+0A8h+var_58]
0x18001576b  mov     [rsp+0A8h+var_3C], 1
0x180015773  mov     [rsp+0A8h+var_78], edx
0x180015777  mov     edx, [rsp+0A8h+var_78]
0x18001577b  mov     rcx, [r10+20h]; RegHandle
0x18001577f  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x180015784  mov     [rsp+0A8h+UserData], rax; UserData
0x180015789  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x180015791  call    cs:__imp_EventWriteTransfer
0x180015798  nop     dword ptr [rax+rax+00h]
0x18001579d  mov     rax, rbx
0x1800157a0  mov     rcx, [rsp+0A8h+var_18]
0x1800157a8  xor     rcx, rsp; StackCookie
0x1800157ab  call    __security_check_cookie
0x1800157b0  add     rsp, 0A0h
0x1800157b7  pop     rbx
0x1800157b8  retn
```
