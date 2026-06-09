# CInterceptor_IWbemSyncProvider::SetContainer(IUnknown *)

- ea: `0x140024820`
- end: `0x1400248e6`
- name: `?SetContainer@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIUnknown@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400234b8`
- `0x140024820`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140024871`
- `wbemcomn!GetMemLogObject` at `0x140024894`
- `wbemcomn!GetMemLogObject` at `0x140024871`
- `wbemcomn!GetMemLogObject` at `0x140024894`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002487c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400248a4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002487c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400248a4`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::SetContainer(
        CInterceptor_IWbemSyncProvider *this,
        struct IUnknown *a2)
{
  int v2; // ebx
  _QWORD *v3; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  CMemoryLog *v8; // rax

  if ( a2 )
  {
    v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID__IWmiProviderQuota,
           (char *)this + 256);
    if ( v2 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v2);
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 175;
      v7 = (unsigned int)v2;
LABEL_13:
      WPP_SF_d(v3[2], v6, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, v7);
    }
  }
  else
  {
    v8 = GetMemLogObject();
    v2 = -2147217400;
    CMemoryLog::Write(v8, -2147217400);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 176;
      v7 = 2147749896LL;
      goto LABEL_13;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140024820  push    rbx
0x140024822  sub     rsp, 20h
0x140024826  mov     r9, rdx
0x140024829  test    rdx, rdx
0x14002482c  jz      short loc_140024894
0x14002482e  mov     rax, [rdx]
0x140024831  lea     r8, [rcx+100h]
0x140024838  lea     rdx, IID__IWmiProviderQuota
0x14002483f  mov     rcx, r9
0x140024842  mov     rax, [rax]
0x140024845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002484a  mov     ebx, eax
0x14002484c  test    eax, eax
0x14002484e  js      short loc_140024871
0x140024850  mov     rcx, cs:WPP_GLOBAL_Control
0x140024857  lea     rax, WPP_GLOBAL_Control
0x14002485e  cmp     rcx, rax
0x140024861  jz      short loc_140024869
0x140024863  test    byte ptr [rcx+1Ch], 4
0x140024867  jnz     short loc_140024884
0x140024869  mov     eax, ebx
0x14002486b  add     rsp, 20h
0x14002486f  pop     rbx
0x140024870  retn
0x140024871  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140024877  mov     rcx, rax
0x14002487a  mov     edx, ebx
0x14002487c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140024882  jmp     short loc_140024850
0x140024884  cmp     byte ptr [rcx+19h], 2
0x140024888  jb      short loc_140024869
0x14002488a  mov     edx, 0AFh
0x14002488f  mov     r9d, ebx
0x140024892  jmp     short loc_1400248D4
0x140024894  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002489a  mov     ebx, 80041008h
0x14002489f  mov     rcx, rax
0x1400248a2  mov     edx, ebx
0x1400248a4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400248aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248b1  lea     rax, WPP_GLOBAL_Control
0x1400248b8  cmp     rcx, rax
0x1400248bb  jz      short loc_140024869
0x1400248bd  test    byte ptr [rcx+1Ch], 4
0x1400248c1  jz      short loc_140024869
0x1400248c3  cmp     byte ptr [rcx+19h], 2
0x1400248c7  jb      short loc_140024869
0x1400248c9  mov     edx, 0B0h
0x1400248ce  mov     r9d, 80041008h
0x1400248d4  mov     rcx, [rcx+10h]
0x1400248d8  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x1400248df  call    WPP_SF_d
0x1400248e4  jmp     short loc_140024869
```
