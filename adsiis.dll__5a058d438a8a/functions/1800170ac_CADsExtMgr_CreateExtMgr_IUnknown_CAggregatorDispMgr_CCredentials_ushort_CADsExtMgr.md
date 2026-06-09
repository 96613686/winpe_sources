# CADsExtMgr::CreateExtMgr(IUnknown *,CAggregatorDispMgr *,CCredentials &,ushort *,CADsExtMgr * *)

- ea: `0x1800170ac`
- end: `0x18001718e`
- name: `?CreateExtMgr@CADsExtMgr@@SAJPEAUIUnknown@@PEAVCAggregatorDispMgr@@AEAVCCredentials@@PEAGPEAPEAV1@@Z`
- size: `226`
- prototype: `__int64 __usercall@<rax>(LPUNKNOWN pUnkOuter@<rcx>, struct CAggregatorDispMgr *@<rdx>, struct CCredentials *@<r8>, unsigned __int16 *@<r9>, struct CADsExtMgr **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000549c`

## callees

- `0x1800010b0`
- `0x1800170ac`
- `0x180017480`
- `0x180017c28`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017116`
- `msvcrt!_wcsicmp` at `0x180017116`
- `KERNEL32!EnterCriticalSection` at `0x1800170fe`
- `KERNEL32!EnterCriticalSection` at `0x1800170fe`
- `KERNEL32!LeaveCriticalSection` at `0x180017146`
- `KERNEL32!LeaveCriticalSection` at `0x180017146`

## pseudocode

```c
__int64 __fastcall CADsExtMgr::CreateExtMgr(
        LPUNKNOWN pUnkOuter,
        struct CAggregatorDispMgr *a2,
        LONG *a3,
        unsigned __int16 *a4,
        struct CADsExtMgr **a5)
{
  struct CADsExtMgr *v9; // rbx
  wchar_t *i; // rdi
  struct _class_entry *v11; // r8
  unsigned int v12; // ecx

  v9 = (struct CADsExtMgr *)operator new(0x18u);
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = 0;
    *(_QWORD *)v9 = &CADsExtMgr::`vftable';
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 2) = a2;
    EnterCriticalSection(&g_ExtCritSect);
    for ( i = gpClassHead; i; i = (wchar_t *)*((_QWORD *)i + 66) )
    {
      if ( !_wcsicmp(i, a4) )
      {
        *((_QWORD *)v9 + 1) = MakeCopyofClassEntry(i);
        goto LABEL_8;
      }
    }
    *((_QWORD *)v9 + 1) = 0;
LABEL_8:
    LeaveCriticalSection(&g_ExtCritSect);
    v11 = (struct _class_entry *)*((_QWORD *)v9 + 1);
    if ( v11 )
      v12 = ADSILoadExtensions2(pUnkOuter, a3, v11);
    else
      v12 = 0;
    *a5 = v9;
    return v12;
  }
  else
  {
    *a5 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800170ac  push    rbx
0x1800170ae  push    rbp
0x1800170af  push    rsi
0x1800170b0  push    rdi
0x1800170b1  push    r14
0x1800170b3  sub     rsp, 20h
0x1800170b7  mov     r14, rcx
0x1800170ba  mov     rsi, r9
0x1800170bd  mov     ecx, 18h; Size
0x1800170c2  mov     rbp, r8
0x1800170c5  mov     rdi, rdx
0x1800170c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800170cd  mov     rbx, rax
0x1800170d0  test    rax, rax
0x1800170d3  jz      loc_180017172
0x1800170d9  lea     rax, ??_7CADsExtMgr@@6B@; const CADsExtMgr::`vftable'
0x1800170e0  mov     qword ptr [rbx+8], 0
0x1800170e8  mov     [rbx], rax
0x1800170eb  lea     rcx, ?g_ExtCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800170f2  mov     qword ptr [rbx+10h], 0
0x1800170fa  mov     [rbx+10h], rdi
0x1800170fe  call    cs:__imp_EnterCriticalSection
0x180017104  mov     rdi, cs:?gpClassHead@@3PEAU_class_entry@@EA; _class_entry * gpClassHead
0x18001710b  test    rdi, rdi
0x18001710e  jz      short loc_180017137
0x180017110  mov     rdx, rsi; String2
0x180017113  mov     rcx, rdi; String1
0x180017116  call    cs:__imp__wcsicmp
0x18001711c  test    eax, eax
0x18001711e  jz      short loc_180017129
0x180017120  mov     rdi, [rdi+210h]
0x180017127  jmp     short loc_18001710B
0x180017129  mov     rcx, rdi; Source
0x18001712c  call    ?MakeCopyofClassEntry@@YAPEAU_class_entry@@PEAU1@@Z; MakeCopyofClassEntry(_class_entry *)
0x180017131  mov     [rbx+8], rax
0x180017135  jmp     short loc_18001713F
0x180017137  mov     qword ptr [rbx+8], 0
0x18001713f  lea     rcx, ?g_ExtCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017146  call    cs:__imp_LeaveCriticalSection
0x18001714c  mov     r8, [rbx+8]; struct _class_entry *
0x180017150  test    r8, r8
0x180017153  jz      short loc_180017164
0x180017155  mov     rdx, rbp; this
0x180017158  mov     rcx, r14; pUnkOuter
0x18001715b  call    ?ADSILoadExtensions2@@YAJPEAUIUnknown@@AEAVCCredentials@@PEAU_class_entry@@@Z; ADSILoadExtensions2(IUnknown *,CCredentials &,_class_entry *)
0x180017160  mov     ecx, eax
0x180017162  jmp     short loc_180017166
0x180017164  xor     ecx, ecx
0x180017166  mov     rax, [rsp+48h+arg_20]
0x18001716b  mov     [rax], rbx
0x18001716e  mov     eax, ecx
0x180017170  jmp     short loc_180017183
0x180017172  mov     rax, [rsp+48h+arg_20]
0x180017177  mov     qword ptr [rax], 0
0x18001717e  mov     eax, 8007000Eh
0x180017183  add     rsp, 20h
0x180017187  pop     r14
0x180017189  pop     rdi
0x18001718a  pop     rsi
0x18001718b  pop     rbp
0x18001718c  pop     rbx
0x18001718d  retn
```
