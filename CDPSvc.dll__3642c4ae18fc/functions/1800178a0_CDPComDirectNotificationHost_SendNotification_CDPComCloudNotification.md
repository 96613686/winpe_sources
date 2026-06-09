# CDPComDirectNotificationHost::SendNotification(CDPComCloudNotification *)

- ea: `0x1800178a0`
- end: `0x180017941`
- name: `?SendNotification@CDPComDirectNotificationHost@@UEAAJPEAUCDPComCloudNotification@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CDPComDirectNotificationHost *__hidden this, struct CDPComCloudNotification *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003e60`
- `0x1800130ec`
- `0x1800178a0`
- `0x180017948`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateCloudNotification` at `0x1800178e6`
- `cdp!CDPCreateCloudNotification` at `0x1800178e6`

## string_xrefs

- `0x1800178f8`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDPComDirectNotificationHost::SendNotification(
        CDPComDirectNotificationHost *this,
        struct CDPComCloudNotification *a2)
{
  __int64 v3; // r9
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx
  int v8[2]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base **v9; // [rsp+28h] [rbp-20h]
  std::_Ref_count_base *v10[2]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)v10 = 0;
  *(_QWORD *)v8 = 0;
  v9 = v10;
  if ( a2 )
  {
    v5 = CDPCreateCloudNotification(*(_QWORD *)a2, *((_QWORD *)a2 + 1), v8);
    if ( v5 >= 0 )
      goto LABEL_6;
    v3 = (unsigned int)v5;
    v4 = 1022;
  }
  else
  {
    v3 = 2147942487LL;
    v4 = 1021;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
    (const char *)v3,
    v8[0]);
LABEL_6:
  cdp::detail::address_of<ICDPCloudNotification>::~address_of<ICDPCloudNotification>(v8);
  v6 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base *))(**((_QWORD **)this + 3) + 32LL))(
         *((_QWORD *)this + 3),
         v10[0]);
  if ( v10[1] )
    std::_Ref_count_base::_Decref(v10[1]);
  return v6;
}

```

## disassembly

```asm
0x1800178a0  push    rbx
0x1800178a2  sub     rsp, 40h
0x1800178a6  mov     rax, rdx
0x1800178a9  mov     rbx, rcx
0x1800178ac  xorps   xmm0, xmm0
0x1800178af  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x1800178b5  mov     qword ptr [rsp+48h+var_28], 0; int
0x1800178be  lea     rcx, [rsp+48h+var_18]
0x1800178c3  mov     [rsp+48h+var_20], rcx
0x1800178c8  test    rdx, rdx
0x1800178cb  jnz     short loc_1800178DA
0x1800178cd  mov     r9d, 80070057h
0x1800178d3  mov     edx, 3FDh
0x1800178d8  jmp     short loc_1800178F8
0x1800178da  lea     r8, [rsp+48h+var_28]
0x1800178df  mov     rdx, [rdx+8]
0x1800178e3  mov     rcx, [rax]
0x1800178e6  call    cs:__imp_CDPCreateCloudNotification
0x1800178ec  test    eax, eax
0x1800178ee  jns     short loc_180017909
0x1800178f0  mov     r9d, eax; char *
0x1800178f3  mov     edx, 3FEh; void *
0x1800178f8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800178ff  mov     rcx, [rsp+48h]; this
0x180017904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017909  lea     rcx, [rsp+48h+var_28]
0x18001790e  call    ??1?$address_of@VICDPCloudNotification@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCloudNotification>::~address_of<ICDPCloudNotification>(void)
0x180017913  mov     rcx, [rbx+18h]
0x180017917  mov     rax, [rcx]
0x18001791a  mov     rdx, [rsp+48h+var_18]
0x18001791f  mov     rax, [rax+20h]
0x180017923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017928  mov     ebx, eax
0x18001792a  mov     rcx, [rsp+48h+var_18+8]; this
0x18001792f  test    rcx, rcx
0x180017932  jz      short loc_180017939
0x180017934  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017939  mov     eax, ebx
0x18001793b  add     rsp, 40h
0x18001793f  pop     rbx
0x180017940  retn
```
