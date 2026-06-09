# Apx::ApfCircuit::~ApfCircuit(void)

- ea: `0x18001665c`
- end: `0x1800167b5`
- name: `??1ApfCircuit@Apx@@UEAA@XZ`
- size: `345`
- prototype: `void __fastcall(Apx::ApfCircuit *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800167c0`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18001665c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016768`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016768`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800166db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166b3`

## pseudocode

```c
void __fastcall Apx::ApfCircuit::~ApfCircuit(Apx::ApfCircuit *this)
{
  __int64 v2; // rax
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &Apx::ApfCircuit::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v2 = *((unsigned int *)this + 20);
  *((_DWORD *)this + 11) = 6;
  *((_DWORD *)this + v2 + 12) = 6;
  if ( ++*((_DWORD *)this + 20) >= 8u )
    *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_BYTE *)this + 528) )
  {
    v4 = (void *)*((_QWORD *)this + 65);
    if ( v4 )
    {
      operator delete(v4, v3);
      *((_QWORD *)this + 65) = 0;
      *((_DWORD *)this + 128) = 0;
    }
  }
  if ( *((_BYTE *)this + 544) )
  {
    v5 = (void *)*((_QWORD *)this + 67);
    if ( v5 )
    {
      operator delete(v5, v3);
      *((_QWORD *)this + 67) = 0;
      *((_DWORD *)this + 133) = 0;
    }
  }
  v6 = (void *)*((_QWORD *)this + 78);
  if ( v6 )
  {
    operator delete(v6, v3);
    *((_QWORD *)this + 78) = 0;
    *((_DWORD *)this + 154) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x18001665c  mov     [rsp+arg_0], rbx
0x180016661  mov     [rsp+arg_8], rbp
0x180016666  push    rdi
0x180016667  sub     rsp, 20h
0x18001666b  lea     rax, ??_7ApfCircuit@Apx@@6B@; const Apx::ApfCircuit::`vftable'
0x180016672  mov     rbx, rcx
0x180016675  mov     [rcx], rax
0x180016678  mov     rcx, cs:WPP_GLOBAL_Control
0x18001667f  lea     rbp, WPP_GLOBAL_Control
0x180016686  cmp     rcx, rbp
0x180016689  jz      short loc_1800166AC
0x18001668b  test    byte ptr [rcx+1Ch], 1
0x18001668f  jz      short loc_1800166AC
0x180016691  cmp     byte ptr [rcx+19h], 5
0x180016695  jb      short loc_1800166AC
0x180016697  mov     rcx, [rcx+10h]
0x18001669b  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x1800166a2  mov     edx, 0Eh
0x1800166a7  call    WPP_SF_
0x1800166ac  lea     rdi, [rbx+58h]
0x1800166b0  mov     rcx, rdi; lpCriticalSection
0x1800166b3  call    cs:__imp_EnterCriticalSection
0x1800166b9  mov     eax, [rbx+50h]
0x1800166bc  mov     ecx, 6
0x1800166c1  mov     [rbx+2Ch], ecx
0x1800166c4  mov     [rbx+rax*4+30h], ecx
0x1800166c8  inc     dword ptr [rbx+50h]
0x1800166cb  cmp     dword ptr [rbx+50h], 8
0x1800166cf  jb      short loc_1800166D8
0x1800166d1  mov     dword ptr [rbx+50h], 0
0x1800166d8  mov     rcx, rdi; lpCriticalSection
0x1800166db  call    cs:__imp_LeaveCriticalSection
0x1800166e1  cmp     byte ptr [rbx+210h], 0
0x1800166e8  jz      short loc_180016710
0x1800166ea  mov     rcx, [rbx+208h]; void *
0x1800166f1  test    rcx, rcx
0x1800166f4  jz      short loc_180016710
0x1800166f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800166fb  mov     qword ptr [rbx+208h], 0
0x180016706  mov     dword ptr [rbx+200h], 0
0x180016710  cmp     byte ptr [rbx+220h], 0
0x180016717  jz      short loc_18001673F
0x180016719  mov     rcx, [rbx+218h]; void *
0x180016720  test    rcx, rcx
0x180016723  jz      short loc_18001673F
0x180016725  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001672a  mov     qword ptr [rbx+218h], 0
0x180016735  mov     dword ptr [rbx+214h], 0
0x18001673f  mov     rcx, [rbx+270h]; void *
0x180016746  test    rcx, rcx
0x180016749  jz      short loc_180016765
0x18001674b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016750  mov     qword ptr [rbx+270h], 0
0x18001675b  mov     dword ptr [rbx+268h], 0
0x180016765  mov     rcx, rdi; lpCriticalSection
0x180016768  call    cs:__imp_DeleteCriticalSection
0x18001676e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016775  cmp     rcx, rbp
0x180016778  jz      short loc_18001679B
0x18001677a  test    byte ptr [rcx+1Ch], 1
0x18001677e  jz      short loc_18001679B
0x180016780  cmp     byte ptr [rcx+19h], 5
0x180016784  jb      short loc_18001679B
0x180016786  mov     rcx, [rcx+10h]
0x18001678a  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x180016791  mov     edx, 0Fh
0x180016796  call    WPP_SF_
0x18001679b  mov     rbp, [rsp+28h+arg_8]
0x1800167a0  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x1800167a7  mov     [rbx], rax
0x1800167aa  mov     rbx, [rsp+28h+arg_0]
0x1800167af  add     rsp, 20h
0x1800167b3  pop     rdi
0x1800167b4  retn
```
