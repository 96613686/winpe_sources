# CPimcContext::ExecuteUpdates(void)

- ea: `0x180006f5c`
- end: `0x1800070b6`
- name: `?ExecuteUpdates@CPimcContext@@QEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(CPimcContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800071ec`

## callees

- `0x180006f5c`
- `0x180007ce8`
- `0x18000cdb0`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006f87`
- `KERNEL32!EnterCriticalSection` at `0x180006f87`
- `KERNEL32!LeaveCriticalSection` at `0x180006f9d`
- `KERNEL32!LeaveCriticalSection` at `0x180006f9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPimcContext::ExecuteUpdates(CPimcContext *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // esi
  LPVOID v4; // rbx
  LPVOID *ComObject; // rax
  unsigned int v6; // edi
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  LPVOID v9; // [rsp+28h] [rbp-30h]
  LPVOID v10[2]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  v3 = *((_DWORD *)this + 48);
  *((_DWORD *)this + 48) = 0;
  LeaveCriticalSection(v2);
  v4 = 0;
  v9 = 0;
  if ( !v3 )
  {
LABEL_15:
    v6 = 0;
    goto LABEL_16;
  }
  ComObject = ComUtils::GitComLockableWrapper<ITabletContextP>::GetComObject((unsigned int *)this + 74, v10);
  if ( *ComObject )
  {
    v8 = 0;
    v4 = *ComObject;
    *ComObject = 0;
    v8 = 0;
    v9 = v4;
  }
  if ( v10[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10[0] + 16LL))(v10[0]);
  if ( v4 )
  {
    if ( (v3 & 1) != 0 )
      (*(void (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v4 + 248LL))(v4, v10);
    if ( (v3 & 4) != 0 && (*((_BYTE *)this + 240) & 2) == 0 )
      (*(void (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v4 + 232LL))(v4, 0, &v8);
    if ( (v3 & 2) != 0 && (*((_BYTE *)this + 240) & 2) == 0 )
      (*(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v4 + 232LL))(v4, 1, &v8);
    goto LABEL_15;
  }
  v6 = -2147024809;
LABEL_16:
  if ( v4 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180006f5c  mov     [rsp+arg_8], rbx
0x180006f61  mov     [rsp+arg_10], rsi
0x180006f66  push    rdi
0x180006f67  sub     rsp, 50h
0x180006f6b  mov     rax, cs:__security_cookie
0x180006f72  xor     rax, rsp
0x180006f75  mov     [rsp+58h+var_18], rax
0x180006f7a  mov     rdi, rcx
0x180006f7d  lea     rbx, [rcx+0C8h]
0x180006f84  mov     rcx, rbx; lpCriticalSection
0x180006f87  call    cs:__imp_EnterCriticalSection
0x180006f8d  mov     esi, [rdi+0C0h]
0x180006f93  and     dword ptr [rdi+0C0h], 0
0x180006f9a  mov     rcx, rbx; lpCriticalSection
0x180006f9d  call    cs:__imp_LeaveCriticalSection
0x180006fa3  xor     ebx, ebx
0x180006fa5  mov     [rsp+58h+var_30], rbx
0x180006faa  test    esi, esi
0x180006fac  jz      loc_180007078
0x180006fb2  lea     rcx, [rdi+128h]
0x180006fb9  lea     rdx, [rsp+58h+var_28]
0x180006fbe  call    ?GetComObject@?$GitComLockableWrapper@UITabletContextP@@@ComUtils@@QEAA?AV?$CComPtr@UITabletContextP@@@ATL@@XZ; ComUtils::GitComLockableWrapper<ITabletContextP>::GetComObject(void)
0x180006fc3  nop
0x180006fc4  cmp     [rax], rbx
0x180006fc7  jz      short loc_180006FE5
0x180006fc9  and     [rsp+58h+var_38], rbx
0x180006fce  mov     rbx, [rax]
0x180006fd1  and     qword ptr [rax], 0
0x180006fd5  mov     [rsp+58h+var_38], rbx
0x180006fda  and     [rsp+58h+var_38], 0
0x180006fe0  mov     [rsp+58h+var_30], rbx
0x180006fe5  mov     rcx, [rsp+58h+var_28]
0x180006fea  test    rcx, rcx
0x180006fed  jz      short loc_180006FFC
0x180006fef  mov     rax, [rcx]
0x180006ff2  mov     rax, [rax+10h]
0x180006ff6  call    cs:__guard_dispatch_icall_fptr
0x180006ffc  test    rbx, rbx
0x180006fff  jz      loc_1800070AE
0x180007005  test    sil, 1
0x180007009  jz      short loc_180007023
0x18000700b  mov     rax, [rbx]
0x18000700e  lea     rdx, [rsp+58h+var_28]
0x180007013  mov     rcx, rbx
0x180007016  mov     rax, [rax+0F8h]
0x18000701d  call    cs:__guard_dispatch_icall_fptr
0x180007023  test    sil, 4
0x180007027  jz      short loc_18000704C
0x180007029  test    byte ptr [rdi+0F0h], 2
0x180007030  jnz     short loc_18000704C
0x180007032  mov     rax, [rbx]
0x180007035  lea     r8, [rsp+58h+var_38]
0x18000703a  xor     edx, edx
0x18000703c  mov     rcx, rbx
0x18000703f  mov     rax, [rax+0E8h]
0x180007046  call    cs:__guard_dispatch_icall_fptr
0x18000704c  test    sil, 2
0x180007050  jz      short loc_180007078
0x180007052  test    byte ptr [rdi+0F0h], 2
0x180007059  jnz     short loc_180007078
0x18000705b  mov     rax, [rbx]
0x18000705e  lea     r8, [rsp+58h+var_38]
0x180007063  mov     edx, 1
0x180007068  mov     rcx, rbx
0x18000706b  mov     rax, [rax+0E8h]
0x180007072  call    cs:__guard_dispatch_icall_fptr
0x180007078  xor     edi, edi
0x18000707a  test    rbx, rbx
0x18000707d  jz      short loc_18000708F
0x18000707f  mov     rcx, [rbx]
0x180007082  mov     rax, [rcx+10h]
0x180007086  mov     rcx, rbx
0x180007089  call    cs:__guard_dispatch_icall_fptr
0x18000708f  mov     eax, edi
0x180007091  mov     rcx, [rsp+58h+var_18]
0x180007096  xor     rcx, rsp; StackCookie
0x180007099  call    __security_check_cookie
0x18000709e  mov     rbx, [rsp+58h+arg_8]
0x1800070a3  mov     rsi, [rsp+58h+arg_10]
0x1800070a8  add     rsp, 50h
0x1800070ac  pop     rdi
0x1800070ad  retn
0x1800070ae  mov     edi, 80070057h
0x1800070b3  jmp     short loc_18000707A
```
