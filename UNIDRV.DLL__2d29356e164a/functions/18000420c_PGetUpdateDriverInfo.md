# PGetUpdateDriverInfo

- ea: `0x18000420c`
- end: `0x18000444c`
- name: `PGetUpdateDriverInfo`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025780`

## callees

- `0x180003d90`
- `0x18000420c`
- `0x180004454`
- `0x18000490c`
- `0x180005100`
- `0x180005620`
- `0x180005bf0`
- `0x180007220`
- `0x1800073f0`
- `0x1800487e0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800042d2`
- `KERNEL32!LocalFree` at `0x1800043e4`
- `KERNEL32!LocalFree` at `0x18000442c`
- `KERNEL32!LocalFree` at `0x1800042d2`
- `KERNEL32!LocalFree` at `0x1800043e4`
- `KERNEL32!LocalFree` at `0x18000442c`
- `KERNEL32!LocalAlloc` at `0x180004282`
- `KERNEL32!LocalAlloc` at `0x1800043f9`
- `KERNEL32!LocalAlloc` at `0x180004282`
- `KERNEL32!LocalAlloc` at `0x1800043f9`

## pseudocode

```c
__int64 __fastcall PGetUpdateDriverInfo(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _BYTE *v11; // r14
  HLOCAL v12; // rax
  void *v13; // rdi
  int v14; // ebp
  _BYTE *v15; // rdi
  __int64 v16; // r9
  unsigned int v17; // ebp
  __int64 v18; // rdi
  HLOCAL v20; // rax
  _BYTE v21[512]; // [rsp+30h] [rbp-448h] BYREF
  _BYTE v22[512]; // [rsp+230h] [rbp-248h] BYREF

  v11 = (_BYTE *)(a8 + 48);
  if ( *(_DWORD *)(a8 + 40) != *(_DWORD *)(a5 + 12) )
    v11 = 0;
  if ( !a7 || (v15 = (_BYTE *)(a7 + *(unsigned __int16 *)(a7 + 68) + 48LL)) == 0 )
  {
    if ( *(_DWORD *)(a5 + 20) > 0x100u )
      return 0;
    v12 = LocalAlloc(0, 0x400u);
    v13 = v12;
    if ( !v12
      || !(unsigned int)BinitDefaultOptionArray(v12, a5)
      || (v14 = 1, !(unsigned int)GPDSeparateOptionArray(a5, (_DWORD)v13, (unsigned int)v21, 256, 0)) )
    {
      WriteDbgTraceErrorGpd((__int64)"GPDInitDefaultOptions", "InitDefaultOptions: internal failure.");
      v14 = 0;
      if ( !v13 )
        return 0;
    }
    LocalFree(v13);
    if ( !v14 )
      return 0;
    v15 = v21;
  }
  if ( !v11 )
  {
    if ( !(unsigned int)GPDInitDefaultOptions(a5, v22, 256, 1) )
      return 0;
    v11 = v22;
  }
  GPDCombineOptionArray(a5, (__int64)a4, 256, (__int64)v15, (__int64)v11);
  BMergeFormToTrayAssignments(a1);
  GPDResolveUIConflicts(a5);
  v17 = 0;
  if ( a3 )
    LocalFree(a3);
  v18 = 0;
  if ( !a4 )
  {
    v20 = LocalAlloc(0x40u, 0x400u);
    a4 = v20;
    if ( !v20 )
    {
LABEL_25:
      if ( !a4 )
        goto LABEL_16;
LABEL_26:
      LocalFree(a4);
      goto LABEL_16;
    }
    v17 = 1;
    if ( !(unsigned int)BinitDefaultOptionArray(v20, a5) )
      goto LABEL_26;
  }
  v18 = PINFOHDRcreateSnapshot(a5, (__int64)a4, v17, v16);
  if ( v17 )
    goto LABEL_25;
LABEL_16:
  if ( !v18 || !*(_DWORD *)(v18 + 60) )
    return 0;
  return v18 + *(unsigned int *)(v18 + 60);
}

```

## disassembly

```asm
0x18000420c  mov     [rsp+arg_8], rbx
0x180004211  push    rbp
0x180004212  push    rsi
0x180004213  push    rdi
0x180004214  push    r12
0x180004216  push    r13
0x180004218  push    r14
0x18000421a  push    r15
0x18000421c  sub     rsp, 440h
0x180004223  mov     rax, cs:__security_cookie
0x18000422a  xor     rax, rsp
0x18000422d  mov     [rsp+478h+var_48], rax
0x180004235  mov     rax, [rsp+478h+arg_38]
0x18000423d  mov     r12, rcx
0x180004240  mov     rsi, [rsp+478h+arg_20]
0x180004248  mov     rbx, r9
0x18000424b  mov     rdx, [rsp+478h+arg_30]
0x180004253  mov     r15, r8
0x180004256  mov     r13d, 100h
0x18000425c  mov     ecx, [rax+28h]
0x18000425f  lea     r14, [rax+30h]
0x180004263  xor     eax, eax
0x180004265  cmp     ecx, [rsi+0Ch]
0x180004268  cmovnz  r14, rax
0x18000426c  test    rdx, rdx
0x18000426f  jnz     short loc_1800042E7
0x180004271  cmp     [rsi+14h], r13d
0x180004275  ja      loc_18000436B
0x18000427b  mov     edx, 400h; uBytes
0x180004280  xor     ecx, ecx; uFlags
0x180004282  call    cs:__imp_LocalAlloc
0x180004288  mov     rdi, rax
0x18000428b  test    rax, rax
0x18000428e  jz      loc_180004398
0x180004294  mov     rdx, rsi
0x180004297  mov     rcx, rax
0x18000429a  call    BinitDefaultOptionArray
0x18000429f  test    eax, eax
0x1800042a1  jz      loc_180004398
0x1800042a7  mov     r9d, r13d
0x1800042aa  mov     dword ptr [rsp+478h+var_458], 0
0x1800042b2  lea     r8, [rsp+478h+var_448]
0x1800042b7  mov     rdx, rdi
0x1800042ba  mov     rcx, rsi
0x1800042bd  mov     ebp, 1
0x1800042c2  call    GPDSeparateOptionArray
0x1800042c7  test    eax, eax
0x1800042c9  jz      loc_180004398
0x1800042cf  mov     rcx, rdi; hMem
0x1800042d2  call    cs:__imp_LocalFree
0x1800042d8  test    ebp, ebp
0x1800042da  jz      loc_18000436B
0x1800042e0  lea     rdi, [rsp+478h+var_448]
0x1800042e5  jmp     short loc_1800042F8
0x1800042e7  movzx   edi, word ptr [rdx+44h]
0x1800042eb  add     rdi, 30h ; '0'
0x1800042ef  add     rdi, rdx
0x1800042f2  jz      loc_180004271
0x1800042f8  test    r14, r14
0x1800042fb  jz      loc_1800043B7
0x180004301  mov     r9, rdi
0x180004304  mov     [rsp+478h+var_458], r14
0x180004309  mov     r8d, r13d
0x18000430c  mov     rdx, rbx
0x18000430f  mov     rcx, rsi
0x180004312  call    GPDCombineOptionArray
0x180004317  mov     rcx, r12
0x18000431a  call    BMergeFormToTrayAssignments
0x18000431f  mov     r9d, 2
0x180004325  mov     r8d, r13d
0x180004328  mov     rdx, rbx
0x18000432b  mov     rcx, rsi; int
0x18000432e  call    GPDResolveUIConflicts
0x180004333  xor     ebp, ebp
0x180004335  test    r15, r15
0x180004338  jnz     loc_1800043E1
0x18000433e  xor     edi, edi
0x180004340  test    rbx, rbx
0x180004343  jz      loc_1800043EF
0x180004349  mov     r8d, ebp
0x18000434c  mov     rdx, rbx
0x18000434f  mov     rcx, rsi
0x180004352  call    PINFOHDRcreateSnapshot
0x180004357  mov     rdi, rax
0x18000435a  test    ebp, ebp
0x18000435c  jnz     loc_180004420
0x180004362  test    rdi, rdi
0x180004365  jnz     loc_180004437
0x18000436b  xor     eax, eax
0x18000436d  mov     rcx, [rsp+478h+var_48]
0x180004375  xor     rcx, rsp; StackCookie
0x180004378  call    __security_check_cookie
0x18000437d  mov     rbx, [rsp+478h+arg_8]
0x180004385  add     rsp, 440h
0x18000438c  pop     r15
0x18000438e  pop     r14
0x180004390  pop     r13
0x180004392  pop     r12
0x180004394  pop     rdi
0x180004395  pop     rsi
0x180004396  pop     rbp
0x180004397  retn
0x180004398  lea     rdx, aInitdefaultopt; "InitDefaultOptions: internal failure."
0x18000439f  lea     rcx, aGpdinitdefault; "GPDInitDefaultOptions"
0x1800043a6  call    WriteDbgTraceErrorGpd
0x1800043ab  xor     ebp, ebp
0x1800043ad  test    rdi, rdi
0x1800043b0  jz      short loc_18000436B
0x1800043b2  jmp     loc_1800042CF
0x1800043b7  mov     r9d, 1
0x1800043bd  lea     rdx, [rsp+478h+var_248]
0x1800043c5  mov     r8d, r13d
0x1800043c8  mov     rcx, rsi
0x1800043cb  call    GPDInitDefaultOptions
0x1800043d0  test    eax, eax
0x1800043d2  jz      short loc_18000436B
0x1800043d4  lea     r14, [rsp+478h+var_248]
0x1800043dc  jmp     loc_180004301
0x1800043e1  mov     rcx, r15; hMem
0x1800043e4  call    cs:__imp_LocalFree
0x1800043ea  jmp     loc_18000433E
0x1800043ef  mov     edx, 400h; uBytes
0x1800043f4  mov     ecx, 40h ; '@'; uFlags
0x1800043f9  call    cs:__imp_LocalAlloc
0x1800043ff  mov     rbx, rax
0x180004402  test    rax, rax
0x180004405  jz      short loc_180004420
0x180004407  mov     rdx, rsi
0x18000440a  mov     rcx, rax
0x18000440d  mov     ebp, 1
0x180004412  call    BinitDefaultOptionArray
0x180004417  test    eax, eax
0x180004419  jz      short loc_180004429
0x18000441b  jmp     loc_180004349
0x180004420  test    rbx, rbx
0x180004423  jz      loc_180004362
0x180004429  mov     rcx, rbx; hMem
0x18000442c  call    cs:__imp_LocalFree
0x180004432  jmp     loc_180004362
0x180004437  cmp     dword ptr [rdi+3Ch], 0
0x18000443b  jz      loc_18000436B
0x180004441  mov     eax, [rdi+3Ch]
0x180004444  add     rax, rdi
0x180004447  jmp     loc_18000436D
```
