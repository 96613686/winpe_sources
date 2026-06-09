# Apx::ApfCircuitFactory::~ApfCircuitFactory(void)

- ea: `0x1800108e8`
- end: `0x1800109cb`
- name: `??1ApfCircuitFactory@Apx@@UEAA@XZ`
- size: `227`
- prototype: `void __fastcall(Apx::ApfCircuitFactory *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800109e0`

## callees

- `0x18000a12c`
- `0x18000c690`
- `0x18000d210`
- `0x1800108e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010977`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010977`

## pseudocode

```c
void __fastcall Apx::ApfCircuitFactory::~ApfCircuitFactory(Apx::ApfCircuitFactory *this)
{
  __int64 v2; // rax
  __int64 v3; // rdx

  *(_QWORD *)this = &Apx::ApfCircuitFactory::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  v2 = *((unsigned int *)this + 14);
  *((_DWORD *)this + 5) = 6;
  *((_DWORD *)this + v2 + 6) = 6;
  if ( ++*((_DWORD *)this + 14) >= 8u )
    *((_DWORD *)this + 14) = 0;
  v3 = *((_QWORD *)this + 17);
  if ( v3 )
  {
    imp_ApxObjectDelete(0, (Apx::ApfVerify *)~v3);
    *((_QWORD *)this + 17) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_88d8f9f30453351596b6a72932727db3_Traceguids);
  }
  Apx::ApfWorkItemQueue::~ApfWorkItemQueue((Apx::ApfCircuitFactory *)((char *)this + 168));
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x1800108e8  mov     [rsp+arg_0], rbx
0x1800108ed  push    rdi
0x1800108ee  sub     rsp, 20h
0x1800108f2  lea     rax, ??_7ApfCircuitFactory@Apx@@6B@; const Apx::ApfCircuitFactory::`vftable'
0x1800108f9  mov     rbx, rcx
0x1800108fc  mov     [rcx], rax
0x1800108ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180010906  lea     rdi, WPP_GLOBAL_Control
0x18001090d  cmp     rcx, rdi
0x180010910  jz      short loc_180010933
0x180010912  test    byte ptr [rcx+1Ch], 1
0x180010916  jz      short loc_180010933
0x180010918  cmp     byte ptr [rcx+19h], 5
0x18001091c  jb      short loc_180010933
0x18001091e  mov     rcx, [rcx+10h]
0x180010922  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x180010929  mov     edx, 0Fh
0x18001092e  call    WPP_SF_
0x180010933  mov     eax, [rbx+38h]
0x180010936  mov     ecx, 6
0x18001093b  mov     [rbx+14h], ecx
0x18001093e  mov     [rbx+rax*4+18h], ecx
0x180010942  inc     dword ptr [rbx+38h]
0x180010945  cmp     dword ptr [rbx+38h], 8
0x180010949  jb      short loc_180010952
0x18001094b  mov     dword ptr [rbx+38h], 0
0x180010952  mov     rdx, [rbx+88h]
0x180010959  test    rdx, rdx
0x18001095c  jz      short loc_180010973
0x18001095e  not     rdx; Apx::ApfVerify *
0x180010961  xor     ecx, ecx; this
0x180010963  call    imp_ApxObjectDelete
0x180010968  mov     qword ptr [rbx+88h], 0
0x180010973  lea     rcx, [rbx+40h]; lpCriticalSection
0x180010977  call    cs:__imp_DeleteCriticalSection
0x18001097d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010984  cmp     rcx, rdi
0x180010987  jz      short loc_1800109AA
0x180010989  test    byte ptr [rcx+1Ch], 1
0x18001098d  jz      short loc_1800109AA
0x18001098f  cmp     byte ptr [rcx+19h], 5
0x180010993  jb      short loc_1800109AA
0x180010995  mov     rcx, [rcx+10h]
0x180010999  lea     r8, WPP_88d8f9f30453351596b6a72932727db3_Traceguids
0x1800109a0  mov     edx, 10h
0x1800109a5  call    WPP_SF_
0x1800109aa  lea     rcx, [rbx+0A8h]; this
0x1800109b1  call    ??1ApfWorkItemQueue@Apx@@UEAA@XZ; Apx::ApfWorkItemQueue::~ApfWorkItemQueue(void)
0x1800109b6  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x1800109bd  mov     [rbx], rax
0x1800109c0  mov     rbx, [rsp+28h+arg_0]
0x1800109c5  add     rsp, 20h
0x1800109c9  pop     rdi
0x1800109ca  retn
```
