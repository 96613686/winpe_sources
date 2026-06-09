# EdgeFlyoutPositioningBehavior::CalculateWindowRect(void)

- ea: `0x1800232b4`
- end: `0x1800233c2`
- name: `?CalculateWindowRect@EdgeFlyoutPositioningBehavior@@AEAA?AUtagRECT@@XZ`
- size: `270`
- prototype: `struct tagRECT *__fastcall(EdgeFlyoutPositioningBehavior *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029c40`

## callees

- `0x180002b20`
- `0x18001049c`
- `0x1800232b4`
- `0x1800234d0`
- `0x1800271a0`

## import_xrefs

- `USER32!MonitorFromPoint` at `0x180023307`
- `USER32!MonitorFromPoint` at `0x18002332c`
- `USER32!MonitorFromPoint` at `0x180023307`
- `USER32!MonitorFromPoint` at `0x18002332c`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180023350`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180023350`

## string_xrefs

- `0x1800232e4`: `pcshell\shell\uxframe\dll\WindowPositioningBehavior.h`

## pseudocode

```c
struct tagRECT *__fastcall EdgeFlyoutPositioningBehavior::CalculateWindowRect(
        EdgeFlyoutPositioningBehavior *this,
        struct tagRECT *__return_ptr retstr,
        __int64 a3,
        const char *a4)
{
  HMONITOR v6; // rax
  int v7; // eax
  LONG left; // ecx
  int v9; // r9d
  LONG right; // ecx
  struct tagRECT v11; // xmm0
  struct tagRECT *result; // rax
  struct tagRECT v13; // [rsp+20h] [rbp-40h] BYREF
  struct tagRECT pt; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT v15; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( *((_DWORD *)this + 9) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x107,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\WindowPositioningBehavior.h",
      a4);
  pt.top = 0;
  MonitorFromPoint(0, 1u);
  *(_QWORD *)&v13.left = 0;
  v15 = 0;
  pt.left = 0;
  v6 = MonitorFromPoint(0, 1u);
  GetWorkAreaAndDpiForMonitorWithFallback(v6, &v15, (unsigned int *)&pt);
  v7 = MulDiv(400, pt.left, 96);
  left = v15.left;
  v9 = *((_DWORD *)this + 8);
  v13.top = v15.top;
  if ( v9 )
    left = v15.right - v7;
  v13.left = left;
  right = v15.left + v7;
  if ( v9 )
    right = v15.right;
  v13.right = right;
  v13.bottom = v15.bottom;
  v11 = *ConstrainRect(&pt, &v13, &v15);
  result = retstr;
  *retstr = v11;
  return result;
}

```

## disassembly

```asm
0x1800232b4  mov     [rsp-8+arg_0], rbx
0x1800232b9  mov     [rsp-8+arg_10], rdi
0x1800232be  push    rbp
0x1800232bf  mov     rbp, rsp
0x1800232c2  sub     rsp, 60h
0x1800232c6  mov     rax, cs:__security_cookie
0x1800232cd  xor     rax, rsp
0x1800232d0  mov     [rbp+var_10], rax
0x1800232d4  cmp     dword ptr [rcx+24h], 0
0x1800232d8  mov     rdi, rdx
0x1800232db  mov     rbx, rcx
0x1800232de  jz      short loc_1800232F6
0x1800232e0  mov     rcx, [rbp+8]; this
0x1800232e4  lea     r8, aPcshellShellUx_1; "pcshell\\shell\\uxframe\\dll\\WindowPos"...
0x1800232eb  mov     edx, 107h; void *
0x1800232f0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800232f6  mov     qword ptr [rbp+pt], 0
0x1800232fe  mov     edx, 1; dwFlags
0x180023303  mov     rcx, qword ptr [rbp+pt]; pt
0x180023307  call    cs:__imp_MonitorFromPoint
0x18002330d  xorps   xmm0, xmm0
0x180023310  mov     qword ptr [rbp+var_40.x], 0
0x180023318  mov     rcx, qword ptr [rbp+var_40.x]; pt
0x18002331c  mov     edx, 1; dwFlags
0x180023321  movups  xmmword ptr [rbp+var_20.left], xmm0
0x180023325  mov     dword ptr [rbp+pt], 0
0x18002332c  call    cs:__imp_MonitorFromPoint
0x180023332  mov     rcx, rax; HMONITOR
0x180023335  lea     r8, [rbp+pt]; unsigned int *
0x180023339  lea     rdx, [rbp+var_20]; struct tagRECT *
0x18002333d  call    ?GetWorkAreaAndDpiForMonitorWithFallback@@YAXPEAUHMONITOR__@@PEAUtagRECT@@PEAI@Z; GetWorkAreaAndDpiForMonitorWithFallback(HMONITOR__ *,tagRECT *,uint *)
0x180023342  mov     edx, dword ptr [rbp+pt]; nNumerator
0x180023345  mov     r8d, 60h ; '`'; nDenominator
0x18002334b  mov     ecx, 190h; nNumber
0x180023350  call    cs:__imp_MulDiv
0x180023356  mov     r8d, [rbp+var_20.left]
0x18002335a  mov     ecx, r8d
0x18002335d  mov     edx, [rbp+var_20.right]
0x180023360  mov     r10d, eax
0x180023363  mov     r9d, [rbx+20h]
0x180023367  sub     edx, eax
0x180023369  mov     eax, [rbp+var_20.top]
0x18002336c  test    r9d, r9d
0x18002336f  mov     [rbp+var_40.y], eax
0x180023372  cmovnz  ecx, edx
0x180023375  lea     rdx, [rbp+var_40]; struct tagRECT
0x180023379  mov     [rbp+var_40.x], ecx
0x18002337c  lea     ecx, [r8+r10]
0x180023380  cmovnz  ecx, [rbp+var_20.right]
0x180023384  lea     r8, [rbp+var_20]; struct tagRECT *
0x180023388  mov     [rbp+var_38], ecx
0x18002338b  mov     ecx, [rbp+var_20.bottom]
0x18002338e  mov     [rbp+var_34], ecx
0x180023391  lea     rcx, [rbp+pt]; lprcDst
0x180023395  call    ?ConstrainRect@@YA?AUtagRECT@@U1@AEBU1@@Z; ConstrainRect(tagRECT,tagRECT const &)
0x18002339a  movups  xmm0, xmmword ptr [rax]
0x18002339d  mov     rax, rdi
0x1800233a0  movdqu  xmmword ptr [rdi], xmm0
0x1800233a4  mov     rcx, [rbp+var_10]
0x1800233a8  xor     rcx, rsp; StackCookie
0x1800233ab  call    __security_check_cookie
0x1800233b0  lea     r11, [rsp+60h+var_s0]
0x1800233b5  mov     rbx, [r11+10h]
0x1800233b9  mov     rdi, [r11+20h]
0x1800233bd  mov     rsp, r11
0x1800233c0  pop     rbp
0x1800233c1  retn
```
