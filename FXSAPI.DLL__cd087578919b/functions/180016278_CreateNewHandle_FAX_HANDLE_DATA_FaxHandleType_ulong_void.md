# CreateNewHandle(_FAX_HANDLE_DATA *,FaxHandleType,ulong,void *)

- ea: `0x180016278`
- end: `0x180016343`
- name: `?CreateNewHandle@@YAPEAU_HANDLE_ENTRY@@PEAU_FAX_HANDLE_DATA@@W4FaxHandleType@@KPEAX@Z`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001634c`
- `0x18001a368`
- `0x180023e50`

## callees

- `0x18000abe4`
- `0x180016278`
- `0x18002bab8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800162de`
- `KERNEL32!EnterCriticalSection` at `0x1800162de`
- `KERNEL32!LeaveCriticalSection` at `0x180016326`
- `KERNEL32!LeaveCriticalSection` at `0x180016326`

## pseudocode

```c
__int64 __fastcall CreateNewHandle(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v9; // rdi
  __int64 *v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids);
  }
  result = pMemAlloc(0x38u);
  v9 = result;
  if ( result )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v10 = *(__int64 **)(a1 + 16);
    *(_QWORD *)v9 = a1 + 8;
    *(_QWORD *)(v9 + 8) = v10;
    *v10 = v9;
    *(_QWORD *)(a1 + 16) = v9;
    *(_DWORD *)(v9 + 16) = a2;
    *(_DWORD *)(v9 + 20) = a3;
    *(_QWORD *)(v9 + 32) = a1;
    *(_QWORD *)(v9 + 40) = a4;
    *(_DWORD *)(v9 + 24) = 0;
    *(_QWORD *)(v9 + 48) = 0;
    ++*(_DWORD *)(a1 + 64);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180016278  push    rbx
0x18001627a  push    rbp
0x18001627b  push    rsi
0x18001627c  push    rdi
0x18001627d  push    r14
0x18001627f  push    r15
0x180016281  sub     rsp, 28h
0x180016285  mov     rbp, r9
0x180016288  mov     r14d, r8d
0x18001628b  mov     r15d, edx
0x18001628e  mov     rsi, rcx
0x180016291  mov     rcx, cs:WPP_GLOBAL_Control
0x180016298  lea     rax, WPP_GLOBAL_Control
0x18001629f  cmp     rcx, rax
0x1800162a2  jz      short loc_1800162C8
0x1800162a4  test    dword ptr [rcx+1Ch], 1000h
0x1800162ab  jz      short loc_1800162C8
0x1800162ad  cmp     byte ptr [rcx+19h], 5
0x1800162b1  jb      short loc_1800162C8
0x1800162b3  mov     rcx, [rcx+10h]
0x1800162b7  lea     r8, WPP_09bf480e846a3bc6581fd59195b9f412_Traceguids
0x1800162be  mov     edx, 0Ah
0x1800162c3  call    WPP_SF_
0x1800162c8  mov     ecx, 38h ; '8'; dwBytes
0x1800162cd  call    pMemAlloc
0x1800162d2  mov     rdi, rax
0x1800162d5  test    rax, rax
0x1800162d8  jz      short loc_180016335
0x1800162da  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800162de  call    cs:__imp_EnterCriticalSection
0x1800162e5  nop     dword ptr [rax+rax+00h]
0x1800162ea  lea     rdx, [rsi+8]
0x1800162ee  mov     rax, [rdx+8]
0x1800162f2  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800162f6  mov     [rdi], rdx
0x1800162f9  mov     [rdi+8], rax
0x1800162fd  mov     [rax], rdi
0x180016300  mov     [rdx+8], rdi
0x180016304  mov     [rdi+10h], r15d
0x180016308  mov     [rdi+14h], r14d
0x18001630c  mov     [rdi+20h], rsi
0x180016310  mov     [rdi+28h], rbp
0x180016314  mov     dword ptr [rdi+18h], 0
0x18001631b  mov     qword ptr [rdi+30h], 0
0x180016323  inc     dword ptr [rsi+40h]
0x180016326  call    cs:__imp_LeaveCriticalSection
0x18001632d  nop     dword ptr [rax+rax+00h]
0x180016332  mov     rax, rdi
0x180016335  add     rsp, 28h
0x180016339  pop     r15
0x18001633b  pop     r14
0x18001633d  pop     rdi
0x18001633e  pop     rsi
0x18001633f  pop     rbp
0x180016340  pop     rbx
0x180016341  retn
```
