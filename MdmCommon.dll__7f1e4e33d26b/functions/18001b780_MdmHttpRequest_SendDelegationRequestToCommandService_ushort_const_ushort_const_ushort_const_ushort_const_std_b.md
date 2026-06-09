# MdmHttpRequest::SendDelegationRequestToCommandService(ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001b780`
- end: `0x18001b8a9`
- name: `?SendDelegationRequestToCommandService@MdmHttpRequest@@UEAAJPEBG000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `297`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, LPCWCH lpWideCharStr, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de4`
- `0x180012e38`
- `0x18001b394`
- `0x18001b780`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SendDelegationRequestToCommandService(
        MdmHttpRequest *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5,
        LPCWCH lpWideCharStr,
        unsigned int *a7,
        __int64 a8)
{
  int ServiceHost; // ebx
  unsigned __int16 *v13; // rdx
  unsigned __int16 *v15[2]; // [rsp+60h] [rbp-68h] BYREF
  __m128i si128; // [rsp+70h] [rbp-58h]

  try
  {
    *(_OWORD *)v15 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15[0]) = 0;
    ServiceHost = MdmSettings::GetServiceHost(v15);
    if ( ServiceHost >= 0 )
    {
      if ( si128.m128i_i64[0] )
      {
        v13 = (unsigned __int16 *)v15;
        if ( si128.m128i_i64[1] > 7uLL )
          v13 = v15[0];
        ServiceHost = MdmHttpRequest::SendDelegationRequest(this, v13, a2, a3, a4, a5, lpWideCharStr, a7, a8);
        std::wstring::~wstring(v15);
      }
      else
      {
        ServiceHost = -2147418113;
        std::wstring::~wstring(v15);
      }
    }
    else
    {
      std::wstring::~wstring(v15);
    }
  }
  catch ( std::exception )
  {
    return (unsigned int)-2147467259;
  }
  *(_OWORD *)v15 = 0;
}

```

## disassembly

```asm
0x18001b780  push    rbx
0x18001b782  push    rsi
0x18001b783  push    rdi
0x18001b784  push    r12
0x18001b786  push    r13
0x18001b788  push    r14
0x18001b78a  push    r15
0x18001b78c  sub     rsp, 90h
0x18001b793  mov     rax, cs:__security_cookie
0x18001b79a  xor     rax, rsp
0x18001b79d  mov     [rsp+0C8h+var_48], rax
0x18001b7a5  mov     r15, r9
0x18001b7a8  mov     r14, r8
0x18001b7ab  mov     rsi, rdx
0x18001b7ae  mov     rdi, rcx
0x18001b7b1  mov     r12, [rsp+0C8h+arg_20]
0x18001b7b9  mov     r13, [rsp+0C8h+arg_28]
0x18001b7c1  mov     rax, [rsp+0C8h+arg_30]
0x18001b7c9  mov     [rsp+0C8h+var_70], rax
0x18001b7ce  mov     rax, [rsp+0C8h+arg_38]
0x18001b7d6  mov     [rsp+0C8h+var_78], rax
0x18001b7db  xorps   xmm0, xmm0
0x18001b7de  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x18001b7e3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b7eb  movdqu  [rsp+0C8h+var_58], xmm1
0x18001b7f1  xor     eax, eax
0x18001b7f3  mov     word ptr [rsp+0C8h+var_68], ax
0x18001b7f8  lea     rcx, [rsp+0C8h+var_68]
0x18001b7fd  call    ?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetServiceHost(std::wstring &)
0x18001b802  mov     ebx, eax
0x18001b804  test    eax, eax
0x18001b806  jns     short loc_18001B815
0x18001b808  lea     rcx, [rsp+0C8h+var_68]
0x18001b80d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b812  nop
0x18001b813  jmp     short loc_18001B884
0x18001b815  cmp     qword ptr [rsp+0C8h+var_58], 0
0x18001b81b  jnz     short loc_18001B82F
0x18001b81d  mov     ebx, 8000FFFFh
0x18001b822  lea     rcx, [rsp+0C8h+var_68]
0x18001b827  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b82c  nop
0x18001b82d  jmp     short loc_18001B884
0x18001b82f  lea     rdx, [rsp+0C8h+var_68]
0x18001b834  cmp     qword ptr [rsp+0C8h+var_58+8], 7
0x18001b83a  cmova   rdx, [rsp+0C8h+var_68]; unsigned __int16 *
0x18001b840  mov     rax, [rsp+0C8h+var_78]
0x18001b845  mov     [rsp+0C8h+var_88], rax; __int64
0x18001b84a  mov     rax, [rsp+0C8h+var_70]
0x18001b84f  mov     [rsp+0C8h+var_90], rax; unsigned int *
0x18001b854  mov     [rsp+0C8h+lpWideCharStr], r13; lpWideCharStr
0x18001b859  mov     [rsp+0C8h+var_A0], r12; __int64
0x18001b85e  mov     [rsp+0C8h+var_A8], r15; unsigned __int16 *
0x18001b863  mov     r9, r14; unsigned __int16 *
0x18001b866  mov     r8, rsi; unsigned __int16 *
0x18001b869  mov     rcx, rdi; this
0x18001b86c  call    ?SendDelegationRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z; MdmHttpRequest::SendDelegationRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::wstring &,ulong *,ushort * *)
0x18001b871  mov     ebx, eax
0x18001b873  lea     rcx, [rsp+0C8h+var_68]
0x18001b878  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b87d  nop
0x18001b87e  jmp     short loc_18001B884
0x18001b880  mov     ebx, dword ptr [rsp+0C8h+var_78]
0x18001b884  mov     eax, ebx
0x18001b886  mov     rcx, [rsp+0C8h+var_48]
0x18001b88e  xor     rcx, rsp; StackCookie
0x18001b891  call    __security_check_cookie
0x18001b896  add     rsp, 90h
0x18001b89d  pop     r15
0x18001b89f  pop     r14
0x18001b8a1  pop     r13
0x18001b8a3  pop     r12
0x18001b8a5  pop     rdi
0x18001b8a6  pop     rsi
0x18001b8a7  pop     rbx
0x18001b8a8  retn
```
