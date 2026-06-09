# HttpRequest::SetBody(uchar const *,unsigned __int64)

- ea: `0x180048c0c`
- end: `0x180048cb7`
- name: `?SetBody@HttpRequest@@QEAAXPEBE_K@Z`
- size: `171`
- prototype: `void(HttpRequest *__hidden this, const unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800354bc`

## callees

- `0x18000dc4f`
- `0x18002008c`
- `0x18003a3e0`
- `0x180048c0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048c44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c3c`

## string_xrefs

- `0x180048ca2`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
void __fastcall HttpRequest::SetBody(IMalloc *this, const unsigned __int8 *a2, unsigned __int64 a3)
{
  void **p_lpVtbl; // rdi
  struct IMallocVtbl *lpVtbl; // rbp
  DWORD LastError; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  p_lpVtbl = (void **)&this[27].lpVtbl;
  lpVtbl = this[27].lpVtbl;
  if ( lpVtbl )
  {
    LastError = GetLastError();
    CoTaskMemFree(lpVtbl);
    SetLastError(LastError);
  }
  *p_lpVtbl = 0;
  if ( !is_mul_ok(a3, 1u) )
  {
    v9 = -2147024362;
LABEL_7:
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x281,
      (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      (const char *)(unsigned int)v9,
      v10);
  }
  v9 = CTCoAllocPolicy::Alloc(this, (a3 * (unsigned __int128)1uLL) >> 64, a3, p_lpVtbl);
  if ( v9 < 0 )
    goto LABEL_7;
  memcpy_0(*p_lpVtbl, a2, a3);
  this[28].lpVtbl = (struct IMallocVtbl *)a3;
}

```

## disassembly

```asm
0x180048c0c  push    rbx
0x180048c0e  push    rbp
0x180048c0f  push    rsi
0x180048c10  push    rdi
0x180048c11  push    r14
0x180048c13  push    r15
0x180048c15  sub     rsp, 28h
0x180048c19  lea     rdi, [rcx+0D8h]
0x180048c20  mov     rsi, r8
0x180048c23  mov     rbp, [rdi]
0x180048c26  mov     r15, rdx
0x180048c29  mov     r14, rcx
0x180048c2c  test    rbp, rbp
0x180048c2f  jz      short loc_180048C4A
0x180048c31  call    cs:__imp_GetLastError
0x180048c37  mov     rcx, rbp; pv
0x180048c3a  mov     ebx, eax
0x180048c3c  call    cs:__imp_CoTaskMemFree
0x180048c42  mov     ecx, ebx; dwErrCode
0x180048c44  call    cs:__imp_SetLastError
0x180048c4a  mov     eax, 1
0x180048c4f  mov     qword ptr [rdi], 0
0x180048c56  mul     rsi
0x180048c59  mov     [rsp+58h+arg_0], 0
0x180048c62  test    rdx, rdx
0x180048c65  jnz     short loc_180048C98
0x180048c67  mov     r9, rdi; void **
0x180048c6a  mov     r8, rax; unsigned __int64
0x180048c6d  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180048c72  test    eax, eax
0x180048c74  js      short loc_180048C9D
0x180048c76  mov     rcx, [rdi]; void *
0x180048c79  mov     r8, rsi; Size
0x180048c7c  mov     rdx, r15; Src
0x180048c7f  call    memcpy_0
0x180048c84  mov     [r14+0E0h], rsi
0x180048c8b  add     rsp, 28h
0x180048c8f  pop     r15
0x180048c91  pop     r14
0x180048c93  pop     rdi
0x180048c94  pop     rsi
0x180048c95  pop     rbp
0x180048c96  pop     rbx
0x180048c97  retn
0x180048c98  mov     eax, 80070216h
0x180048c9d  mov     rcx, [rsp+58h]; this
0x180048ca2  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x180048ca9  mov     r9d, eax; char *
0x180048cac  mov     edx, 281h; void *
0x180048cb1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
