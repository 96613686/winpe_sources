# Apx::ApfCircuit::RemoveIpcLink(void)

- ea: `0x1800177a0`
- end: `0x1800178a9`
- name: `?RemoveIpcLink@ApfCircuit@Apx@@QEAAXXZ`
- size: `265`
- prototype: `void __fastcall(Apx::ApfCircuit *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180010f8c`
- `0x180011ab8`

## callees

- `0x18000a12c`
- `0x18000d2f0`
- `0x1800177a0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017866`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017866`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001783d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001783d`

## pseudocode

```c
void __fastcall Apx::ApfCircuit::RemoveIpcLink(Apx::ApfCircuit *this)
{
  __int64 v2; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4));
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4), 0, 0);
  imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~*((_QWORD *)this + 4));
  *((_QWORD *)this + 4) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v2 = *((unsigned int *)this + 20);
  *((_DWORD *)this + 11) = 3;
  *((_DWORD *)this + v2 + 12) = 3;
  if ( ++*((_DWORD *)this + 20) >= 8u )
    *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
}

```

## disassembly

```asm
0x1800177a0  mov     [rsp+arg_0], rbx
0x1800177a5  mov     [rsp+arg_8], rsi
0x1800177aa  push    rdi
0x1800177ab  sub     rsp, 30h
0x1800177af  mov     rbx, rcx
0x1800177b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177b9  lea     rsi, WPP_GLOBAL_Control
0x1800177c0  cmp     rcx, rsi
0x1800177c3  jz      short loc_1800177E6
0x1800177c5  test    byte ptr [rcx+1Ch], 1
0x1800177c9  jz      short loc_1800177E6
0x1800177cb  cmp     byte ptr [rcx+19h], 5
0x1800177cf  jb      short loc_1800177E6
0x1800177d1  mov     rcx, [rcx+10h]
0x1800177d5  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x1800177dc  mov     edx, 1Ch
0x1800177e1  call    WPP_SF_
0x1800177e6  mov     rcx, [rbx+20h]
0x1800177ea  mov     rax, [rcx]
0x1800177ed  mov     rax, [rax+20h]
0x1800177f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177f6  mov     rcx, [rbx+20h]
0x1800177fa  xor     r8d, r8d
0x1800177fd  xor     edx, edx
0x1800177ff  mov     rax, [rcx]
0x180017802  mov     rax, [rax+10h]
0x180017806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001780b  mov     rdx, [rbx+20h]
0x18001780f  lea     rax, aOnecoreuapDriv_6; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180017816  not     rdx; Apx::ApfVerify *
0x180017819  mov     [rsp+38h+var_18], rax
0x18001781e  xor     ecx, ecx; this
0x180017820  mov     r9d, 1C2h
0x180017826  mov     r8d, 44787041h
0x18001782c  call    imp_ApxObjectDereferenceActual
0x180017831  lea     rcx, [rbx+58h]; lpCriticalSection
0x180017835  mov     qword ptr [rbx+20h], 0
0x18001783d  call    cs:__imp_EnterCriticalSection
0x180017843  mov     eax, [rbx+50h]
0x180017846  mov     ecx, 3
0x18001784b  mov     [rbx+2Ch], ecx
0x18001784e  mov     [rbx+rax*4+30h], ecx
0x180017852  inc     dword ptr [rbx+50h]
0x180017855  cmp     dword ptr [rbx+50h], 8
0x180017859  jb      short loc_180017862
0x18001785b  mov     dword ptr [rbx+50h], 0
0x180017862  lea     rcx, [rbx+58h]; lpCriticalSection
0x180017866  call    cs:__imp_LeaveCriticalSection
0x18001786c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017873  cmp     rcx, rsi
0x180017876  jz      short loc_180017899
0x180017878  test    byte ptr [rcx+1Ch], 1
0x18001787c  jz      short loc_180017899
0x18001787e  cmp     byte ptr [rcx+19h], 5
0x180017882  jb      short loc_180017899
0x180017884  mov     rcx, [rcx+10h]
0x180017888  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x18001788f  mov     edx, 1Dh
0x180017894  call    WPP_SF_
0x180017899  mov     rbx, [rsp+38h+arg_0]
0x18001789e  mov     rsi, [rsp+38h+arg_8]
0x1800178a3  add     rsp, 30h
0x1800178a7  pop     rdi
0x1800178a8  retn
```
