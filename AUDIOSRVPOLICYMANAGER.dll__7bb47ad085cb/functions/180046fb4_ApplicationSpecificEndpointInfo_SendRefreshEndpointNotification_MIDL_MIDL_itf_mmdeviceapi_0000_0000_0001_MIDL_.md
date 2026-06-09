# ApplicationSpecificEndpointInfo::SendRefreshEndpointNotification(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001)

- ea: `0x180046fb4`
- end: `0x180047098`
- name: `?SendRefreshEndpointNotification@ApplicationSpecificEndpointInfo@@AEAAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180046f20`
- `0x1800470a0`

## callees

- `0x18000a384`
- `0x180031960`
- `0x180046fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047013`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047078`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047078`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047045`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x180047061`
- `MMDevAPI!__imp_GenerateMediaEvent` at `0x180047061`

## pseudocode

```c
__int64 __fastcall ApplicationSpecificEndpointInfo::SendRefreshEndpointNotification(
        __int64 a1,
        unsigned int a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  unsigned int *v8; // r14
  unsigned int *i; // rsi
  DWORD CurrentProcessId; // eax
  __int64 v11; // rdx
  int v12[2]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+28h] [rbp-50h]
  unsigned __int64 v14; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a3 < 6 || a2 == 2 || a3 == 0x7FFF )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v8 = *(unsigned int **)(a1 + 64);
    for ( i = *(unsigned int **)(a1 + 56); i != v8; ++i )
    {
      v14 = 0;
      v13 = 0;
      v12[0] = 32;
      v12[1] = 0x100000;
      CurrentProcessId = GetCurrentProcessId();
      v11 = *i;
      *(_QWORD *)&v13 = CurrentProcessId;
      v14 = __PAIR64__(a3, a2);
      GenerateMediaEvent(v12, v11);
    }
    if ( v7 )
      LeaveCriticalSection(v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
      (const char *)0x80070057LL,
      v12[0]);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180046fb4  push    rbx
0x180046fb6  push    rbp
0x180046fb7  push    rsi
0x180046fb8  push    rdi
0x180046fb9  push    r14
0x180046fbb  sub     rsp, 50h
0x180046fbf  mov     rax, cs:__security_cookie
0x180046fc6  xor     rax, rsp
0x180046fc9  mov     [rsp+78h+var_38], rax
0x180046fce  mov     edi, r8d
0x180046fd1  mov     ebp, edx
0x180046fd3  mov     rsi, rcx
0x180046fd6  cmp     r8d, 6
0x180046fda  jl      short loc_18004700C
0x180046fdc  cmp     edx, 2
0x180046fdf  jz      short loc_18004700C
0x180046fe1  cmp     r8d, 7FFFh
0x180046fe8  jz      short loc_18004700C
0x180046fea  mov     rcx, [rsp+78h]; this
0x180046fef  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180046ff6  mov     ebx, 80070057h
0x180046ffb  mov     edx, 30Dh; void *
0x180047000  mov     r9d, ebx; char *
0x180047003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047008  mov     eax, ebx
0x18004700a  jmp     short loc_180047080
0x18004700c  lea     rbx, [rcx+10h]
0x180047010  mov     rcx, rbx; lpCriticalSection
0x180047013  call    cs:__imp_EnterCriticalSection
0x180047019  mov     r14, [rsi+40h]
0x18004701d  mov     rsi, [rsi+38h]
0x180047021  jmp     short loc_18004706B
0x180047023  xorps   xmm0, xmm0
0x180047026  mov     [rsp+78h+var_40], 0
0x18004702f  movdqu  [rsp+78h+var_50], xmm0
0x180047035  mov     [rsp+78h+var_58], 20h ; ' '
0x18004703d  mov     [rsp+78h+var_54], 100000h
0x180047045  call    cs:__imp_GetCurrentProcessId
0x18004704b  mov     edx, [rsi]
0x18004704d  lea     rcx, [rsp+78h+var_58]
0x180047052  mov     eax, eax
0x180047054  mov     qword ptr [rsp+78h+var_50], rax
0x180047059  mov     dword ptr [rsp+78h+var_40], ebp
0x18004705d  mov     dword ptr [rsp+78h+var_40+4], edi
0x180047061  call    cs:__imp_GenerateMediaEvent
0x180047067  add     rsi, 4
0x18004706b  cmp     rsi, r14
0x18004706e  jnz     short loc_180047023
0x180047070  test    rbx, rbx
0x180047073  jz      short loc_18004707E
0x180047075  mov     rcx, rbx; lpCriticalSection
0x180047078  call    cs:__imp_LeaveCriticalSection
0x18004707e  xor     eax, eax
0x180047080  mov     rcx, [rsp+78h+var_38]
0x180047085  xor     rcx, rsp; StackCookie
0x180047088  call    __security_check_cookie
0x18004708d  add     rsp, 50h
0x180047091  pop     r14
0x180047093  pop     rdi
0x180047094  pop     rsi
0x180047095  pop     rbp
0x180047096  pop     rbx
0x180047097  retn
```
