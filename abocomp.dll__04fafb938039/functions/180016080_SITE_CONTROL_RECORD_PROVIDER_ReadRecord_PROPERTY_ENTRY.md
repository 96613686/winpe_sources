# SITE_CONTROL_RECORD_PROVIDER::ReadRecord(PROPERTY_ENTRY *)

- ea: `0x180016080`
- end: `0x1800161f8`
- name: `?ReadRecord@SITE_CONTROL_RECORD_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(SITE_CONTROL_RECORD_PROVIDER *__hidden this, struct PROPERTY_ENTRY *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016080`
- `0x180017554`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800160d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800160d5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016104`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016115`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001616c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800161b0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016104`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016115`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001616c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800161b0`

## pseudocode

```c
__int64 __fastcall SITE_CONTROL_RECORD_PROVIDER::ReadRecord(
        SITE_CONTROL_RECORD_PROVIDER *this,
        struct PROPERTY_ENTRY *a2)
{
  BUFFER *v4; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+68h] [rbp+28h] BYREF
  int v10; // [rsp+70h] [rbp+30h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  v10 = 0;
  v9 = 0;
  ppv = 0;
  if ( !a2 )
    return 0;
  if ( CoCreateInstance(&CLSID_RSCA_W3SVC, 0, 0x15u, &IID_IRSCA_W3SVC, &ppv) >= 0
    && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0) >= 0 )
  {
    v4 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
    if ( *(_DWORD *)BUFFER::QueryPtr(v4) == 1016 || *(_DWORD *)BUFFER::QueryPtr(v4) == 1099 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
             ppv,
             *((unsigned int *)this + 3),
             &v11);
      v6 = 3;
      if ( v5 < 0
        || (v5 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v11 + 24LL))(v11, &v10, &v9), v5 < 0) )
      {
        v9 = v5;
        v10 = 3;
      }
      if ( *(_DWORD *)BUFFER::QueryPtr(v4) == 1099 )
      {
        v6 = WIN32_FROM_HRESULT(v9);
        goto LABEL_18;
      }
      switch ( v10 )
      {
        case 0:
          v6 = 1;
          goto LABEL_18;
        case 1:
          v6 = 2;
          goto LABEL_18;
        case 2:
LABEL_18:
          **((_DWORD **)BUFFER::QueryPtr(v4) + 3) = v6;
          break;
        case 3:
          v6 = 4;
          goto LABEL_18;
      }
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x180016080  push    rbp
0x180016082  push    rbx
0x180016083  push    rdi
0x180016084  mov     rbp, rsp
0x180016087  sub     rsp, 40h
0x18001608b  mov     [rbp+arg_18], 0
0x180016093  mov     rdi, rdx
0x180016096  mov     [rbp+arg_10], 0
0x18001609d  mov     rbx, rcx
0x1800160a0  mov     [rbp+arg_8], 0
0x1800160a7  mov     [rbp+var_10], 0
0x1800160af  test    rdx, rdx
0x1800160b2  jz      loc_1800161EE
0x1800160b8  xor     edx, edx; pUnkOuter
0x1800160ba  lea     rax, [rbp+var_10]
0x1800160be  lea     r9, IID_IRSCA_W3SVC; riid
0x1800160c5  mov     [rsp+40h+ppv], rax; ppv
0x1800160ca  lea     rcx, CLSID_RSCA_W3SVC; rclsid
0x1800160d1  lea     r8d, [rdx+15h]; dwClsContext
0x1800160d5  call    cs:__imp_CoCreateInstance
0x1800160db  test    eax, eax
0x1800160dd  js      loc_1800161BC
0x1800160e3  mov     rcx, [rbp+var_10]
0x1800160e7  xor     edx, edx
0x1800160e9  mov     rax, [rcx]
0x1800160ec  mov     rax, [rax+18h]
0x1800160f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f5  test    eax, eax
0x1800160f7  js      loc_1800161BC
0x1800160fd  add     rdi, 10h
0x180016101  mov     rcx, rdi
0x180016104  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001610a  cmp     dword ptr [rax], 3F8h
0x180016110  jz      short loc_180016127
0x180016112  mov     rcx, rdi
0x180016115  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001611b  cmp     dword ptr [rax], 44Bh
0x180016121  jnz     loc_1800161BC
0x180016127  mov     rcx, [rbp+var_10]
0x18001612b  lea     r8, [rbp+arg_18]
0x18001612f  mov     edx, [rbx+0Ch]
0x180016132  mov     rax, [rcx]
0x180016135  mov     rax, [rax+20h]
0x180016139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001613e  mov     ebx, 3
0x180016143  test    eax, eax
0x180016145  js      short loc_180016163
0x180016147  mov     rcx, [rbp+arg_18]
0x18001614b  lea     r8, [rbp+arg_8]
0x18001614f  lea     rdx, [rbp+arg_10]
0x180016153  mov     rax, [rcx]
0x180016156  mov     rax, [rax+18h]
0x18001615a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001615f  test    eax, eax
0x180016161  jns     short loc_180016169
0x180016163  mov     [rbp+arg_8], eax
0x180016166  mov     [rbp+arg_10], ebx
0x180016169  mov     rcx, rdi
0x18001616c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180016172  cmp     dword ptr [rax], 44Bh
0x180016178  jnz     short loc_180016186
0x18001617a  mov     ecx, [rbp+arg_8]; int
0x18001617d  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180016182  mov     ebx, eax
0x180016184  jmp     short loc_1800161AD
0x180016186  mov     ecx, [rbp+arg_10]
0x180016189  test    ecx, ecx
0x18001618b  jz      short loc_1800161A8
0x18001618d  sub     ecx, 1
0x180016190  jz      short loc_1800161A1
0x180016192  sub     ecx, 1
0x180016195  jz      short loc_1800161AD
0x180016197  cmp     ecx, 1
0x18001619a  jnz     short loc_1800161BC
0x18001619c  lea     ebx, [rcx+3]
0x18001619f  jmp     short loc_1800161AD
0x1800161a1  mov     ebx, 2
0x1800161a6  jmp     short loc_1800161AD
0x1800161a8  mov     ebx, 1
0x1800161ad  mov     rcx, rdi
0x1800161b0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800161b6  mov     rcx, [rax+18h]
0x1800161ba  mov     [rcx], ebx
0x1800161bc  mov     rcx, [rbp+arg_18]
0x1800161c0  test    rcx, rcx
0x1800161c3  jz      short loc_1800161D9
0x1800161c5  mov     rax, [rcx]
0x1800161c8  mov     rax, [rax+10h]
0x1800161cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161d1  mov     [rbp+arg_18], 0
0x1800161d9  mov     rcx, [rbp+var_10]
0x1800161dd  test    rcx, rcx
0x1800161e0  jz      short loc_1800161EE
0x1800161e2  mov     rax, [rcx]
0x1800161e5  mov     rax, [rax+10h]
0x1800161e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161ee  xor     eax, eax
0x1800161f0  add     rsp, 40h
0x1800161f4  pop     rdi
0x1800161f5  pop     rbx
0x1800161f6  pop     rbp
0x1800161f7  retn
```
