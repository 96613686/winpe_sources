# CImpIUpdateInfo::GetPendingColumns(unsigned __int64,unsigned __int64 *,unsigned __int64 * *)

- ea: `0x1800228d0`
- end: `0x180022a3f`
- name: `?GetPendingColumns@CImpIUpdateInfo@@UEAAJ_KPEA_KPEAPEA_K@Z`
- size: `367`
- prototype: `__int64 __fastcall(CImpIUpdateInfo *__hidden this, unsigned __int64, unsigned __int64 *, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180004070`
- `0x180015fb4`
- `0x1800228d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002290a`
- `KERNEL32!GetCurrentThreadId` at `0x18002290a`
- `KERNEL32!LeaveCriticalSection` at `0x1800229f1`
- `KERNEL32!LeaveCriticalSection` at `0x180022a20`
- `KERNEL32!LeaveCriticalSection` at `0x1800229f1`
- `KERNEL32!LeaveCriticalSection` at `0x180022a20`
- `ole32!CoTaskMemFree` at `0x1800229cd`
- `ole32!CoTaskMemFree` at `0x1800229cd`
- `ole32!CoTaskMemAlloc` at `0x180022951`
- `ole32!CoTaskMemAlloc` at `0x180022951`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002292c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002292c`
- `MSDART!UMSEnterCSWraper` at `0x1800228fa`
- `MSDART!UMSEnterCSWraper` at `0x1800228fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIUpdateInfo::GetPendingColumns(
        CImpIUpdateInfo *this,
        __int64 a2,
        unsigned __int64 *a3,
        LPVOID *a4)
{
  __int64 v7; // rbx
  DWORD *v8; // rdi
  __int64 v9; // r15
  unsigned int v10; // ebp
  unsigned __int64 *v11; // rax
  int v12; // ecx
  __int64 v13; // r11
  unsigned int i; // r10d
  unsigned int v15; // ecx
  bool v16; // zf
  __int64 v17; // rcx
  unsigned int v19; // esi
  __int64 v20; // rcx

  v7 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v7);
  v8 = (DWORD *)(v7 + 8);
  if ( !*(_DWORD *)(v7 + 12) )
    *v8 = GetCurrentThreadId();
  ++*(_DWORD *)(v7 + 12);
  ++*(_DWORD *)(v7 + 16);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_DWORD *)(v9 + 152);
  SetErrorInfo(0, 0);
  if ( !a3 || !a4 )
  {
    v12 = -2147024809;
    goto LABEL_18;
  }
  *a3 = 0;
  v11 = (unsigned __int64 *)CoTaskMemAlloc(8LL * v10);
  *a4 = v11;
  if ( !v11 )
  {
    v12 = -2147024882;
LABEL_18:
    v19 = Exit(v12, 0);
    --*(_DWORD *)(v7 + 16);
    v16 = (*(_DWORD *)(v7 + 12))-- == 1;
    if ( v16 )
      *v8 = -1;
    v20 = *(_QWORD *)v7;
    --*(_DWORD *)(v20 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 8));
    return v19;
  }
  LODWORD(v13) = 1;
  for ( i = 1; i <= v10; i += v13 )
  {
    v15 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 280LL) + 8LL * i) + 4LL) & 0xFEFFFFFF;
    if ( !v15 || v15 == 3 )
    {
      *((_QWORD *)*a4 + *a3) = CMetaData::mdGetOrdinal((CMetaData *)(v9 + 304), i - v13);
      *a3 += v13;
    }
  }
  if ( !*a3 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
  --*(_DWORD *)(v7 + 16);
  v16 = (*(_DWORD *)(v7 + 12))-- == 1;
  if ( v16 )
    *v8 = -1;
  v17 = *(_QWORD *)v7;
  --*(_DWORD *)(v17 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800228d0  mov     [rsp+arg_8], rbx
0x1800228d5  mov     [rsp+arg_10], rbp
0x1800228da  push    rsi
0x1800228db  push    rdi
0x1800228dc  push    r13
0x1800228de  push    r14
0x1800228e0  push    r15
0x1800228e2  sub     rsp, 20h
0x1800228e6  mov     rsi, r9
0x1800228e9  mov     r14, r8
0x1800228ec  mov     r13, rcx
0x1800228ef  mov     rbx, [rcx+18h]
0x1800228f3  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800228f7  mov     rcx, rbx
0x1800228fa  call    cs:__imp_UMSEnterCSWraper
0x180022900  lea     rdi, [rbx+8]
0x180022904  cmp     dword ptr [rbx+0Ch], 0
0x180022908  jnz     short loc_180022912
0x18002290a  call    cs:__imp_GetCurrentThreadId
0x180022910  mov     [rdi], eax
0x180022912  inc     dword ptr [rbx+0Ch]
0x180022915  inc     dword ptr [rbx+10h]
0x180022918  mov     [rsp+48h+arg_0], rbx
0x18002291d  mov     r15, [r13+18h]
0x180022921  mov     ebp, [r15+98h]
0x180022928  xor     edx, edx; perrinfo
0x18002292a  xor     ecx, ecx; dwReserved
0x18002292c  call    cs:__imp_SetErrorInfo
0x180022932  test    r14, r14
0x180022935  jz      loc_1800229FB
0x18002293b  test    rsi, rsi
0x18002293e  jz      loc_1800229FB
0x180022944  mov     qword ptr [r14], 0
0x18002294b  mov     ecx, ebp
0x18002294d  shl     rcx, 3; cb
0x180022951  call    cs:__imp_CoTaskMemAlloc
0x180022957  mov     [rsi], rax
0x18002295a  test    rax, rax
0x18002295d  jnz     short loc_180022969
0x18002295f  mov     ecx, 8007000Eh
0x180022964  jmp     loc_180022A00
0x180022969  mov     r11d, 1
0x18002296f  mov     r10d, r11d
0x180022972  cmp     ebp, r11d
0x180022975  jb      short loc_1800229C4
0x180022977  mov     edx, r10d
0x18002297a  mov     rax, [r13+18h]
0x18002297e  mov     rcx, [rax+118h]
0x180022985  mov     rax, [rcx+rdx*8]
0x180022989  mov     ecx, [rax+4]
0x18002298c  and     ecx, 0FEFFFFFFh
0x180022992  jz      short loc_180022999
0x180022994  cmp     ecx, 3
0x180022997  jnz     short loc_1800229BC
0x180022999  movzx   edx, r10w
0x18002299d  sub     dx, r11w; unsigned __int16
0x1800229a1  lea     rcx, [r15+130h]; this
0x1800229a8  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x1800229ad  mov     edx, eax
0x1800229af  mov     rcx, [r14]
0x1800229b2  mov     rax, [rsi]
0x1800229b5  mov     [rax+rcx*8], rdx
0x1800229b9  add     [r14], r11
0x1800229bc  add     r10d, r11d
0x1800229bf  cmp     r10d, ebp
0x1800229c2  jbe     short loc_180022977
0x1800229c4  cmp     qword ptr [r14], 0
0x1800229c8  jnz     short loc_1800229DA
0x1800229ca  mov     rcx, [rsi]; pv
0x1800229cd  call    cs:__imp_CoTaskMemFree
0x1800229d3  mov     qword ptr [rsi], 0
0x1800229da  or      edx, 0FFFFFFFFh
0x1800229dd  add     [rbx+10h], edx
0x1800229e0  add     [rbx+0Ch], edx
0x1800229e3  jnz     short loc_1800229E7
0x1800229e5  mov     [rdi], edx
0x1800229e7  mov     rcx, [rbx]
0x1800229ea  dec     dword ptr [rcx+30h]
0x1800229ed  add     rcx, 8; lpCriticalSection
0x1800229f1  call    cs:__imp_LeaveCriticalSection
0x1800229f7  xor     eax, eax
0x1800229f9  jmp     short loc_180022A28
0x1800229fb  mov     ecx, 80070057h; int
0x180022a00  xor     edx, edx; unsigned int
0x180022a02  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022a07  mov     esi, eax
0x180022a09  or      edx, 0FFFFFFFFh
0x180022a0c  add     [rbx+10h], edx
0x180022a0f  add     [rbx+0Ch], edx
0x180022a12  jnz     short loc_180022A16
0x180022a14  mov     [rdi], edx
0x180022a16  mov     rcx, [rbx]
0x180022a19  dec     dword ptr [rcx+30h]
0x180022a1c  add     rcx, 8; lpCriticalSection
0x180022a20  call    cs:__imp_LeaveCriticalSection
0x180022a26  mov     eax, esi
0x180022a28  mov     rbx, [rsp+48h+arg_8]
0x180022a2d  mov     rbp, [rsp+48h+arg_10]
0x180022a32  add     rsp, 20h
0x180022a36  pop     r15
0x180022a38  pop     r14
0x180022a3a  pop     r13
0x180022a3c  pop     rdi
0x180022a3d  pop     rsi
0x180022a3e  retn
```
