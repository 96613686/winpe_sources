# MdmHttpRequest::SendDelegationRequestToCommandService(ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001bd20`
- end: `0x18001be4a`
- name: `?SendDelegationRequestToCommandService@MdmHttpRequest@@UEAAJPEBG000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, LPCWCH, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de8`
- `0x18001321c`
- `0x18001b924`
- `0x18001bd20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MdmHttpRequest::SendDelegationRequestToCommandService(
        MdmHttpRequest *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWCH lpWideCharStr,
        unsigned int *a7,
        unsigned __int16 **a8)
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
  return (unsigned int)ServiceHost;
}

```

## disassembly

```asm
0x18001bd20  push    rbx
0x18001bd22  push    rsi
0x18001bd23  push    rdi
0x18001bd24  push    r12
0x18001bd26  push    r13
0x18001bd28  push    r14
0x18001bd2a  push    r15
0x18001bd2c  sub     rsp, 90h
0x18001bd33  mov     rax, cs:__security_cookie
0x18001bd3a  xor     rax, rsp
0x18001bd3d  mov     [rsp+0C8h+var_48], rax
0x18001bd45  mov     r15, r9
0x18001bd48  mov     r14, r8
0x18001bd4b  mov     rsi, rdx
0x18001bd4e  mov     rdi, rcx
0x18001bd51  mov     r12, [rsp+0C8h+arg_20]
0x18001bd59  mov     r13, [rsp+0C8h+arg_28]
0x18001bd61  mov     rax, [rsp+0C8h+arg_30]
0x18001bd69  mov     [rsp+0C8h+var_70], rax
0x18001bd6e  mov     rax, [rsp+0C8h+arg_38]
0x18001bd76  mov     [rsp+0C8h+var_78], rax
0x18001bd7b  xorps   xmm0, xmm0
0x18001bd7e  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x18001bd83  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bd8b  movdqu  [rsp+0C8h+var_58], xmm1
0x18001bd91  xor     eax, eax
0x18001bd93  mov     word ptr [rsp+0C8h+var_68], ax
0x18001bd98  lea     rcx, [rsp+0C8h+var_68]
0x18001bd9d  call    ?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmSettings::GetServiceHost(std::wstring &)
0x18001bda2  mov     ebx, eax
0x18001bda4  test    eax, eax
0x18001bda6  jns     short loc_18001BDB5
0x18001bda8  lea     rcx, [rsp+0C8h+var_68]
0x18001bdad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdb2  nop
0x18001bdb3  jmp     short loc_18001BE24
0x18001bdb5  cmp     qword ptr [rsp+0C8h+var_58], 0
0x18001bdbb  jnz     short loc_18001BDCF
0x18001bdbd  mov     ebx, 8000FFFFh
0x18001bdc2  lea     rcx, [rsp+0C8h+var_68]
0x18001bdc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdcc  nop
0x18001bdcd  jmp     short loc_18001BE24
0x18001bdcf  lea     rdx, [rsp+0C8h+var_68]
0x18001bdd4  cmp     qword ptr [rsp+0C8h+var_58+8], 7
0x18001bdda  cmova   rdx, [rsp+0C8h+var_68]; unsigned __int16 *
0x18001bde0  mov     rax, [rsp+0C8h+var_78]
0x18001bde5  mov     [rsp+0C8h+var_88], rax; __int64
0x18001bdea  mov     rax, [rsp+0C8h+var_70]
0x18001bdef  mov     [rsp+0C8h+var_90], rax; unsigned int *
0x18001bdf4  mov     [rsp+0C8h+lpWideCharStr], r13; lpWideCharStr
0x18001bdf9  mov     [rsp+0C8h+var_A0], r12; __int64
0x18001bdfe  mov     [rsp+0C8h+var_A8], r15; unsigned __int16 *
0x18001be03  mov     r9, r14; unsigned __int16 *
0x18001be06  mov     r8, rsi; unsigned __int16 *
0x18001be09  mov     rcx, rdi; this
0x18001be0c  call    ?SendDelegationRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z; MdmHttpRequest::SendDelegationRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::wstring &,ulong *,ushort * *)
0x18001be11  mov     ebx, eax
0x18001be13  lea     rcx, [rsp+0C8h+var_68]
0x18001be18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001be1d  nop
0x18001be1e  jmp     short loc_18001BE24
0x18001be20  mov     ebx, dword ptr [rsp+0C8h+var_78]
0x18001be24  mov     eax, ebx
0x18001be26  mov     rcx, [rsp+0C8h+var_48]
0x18001be2e  xor     rcx, rsp; StackCookie
0x18001be31  call    __security_check_cookie
0x18001be36  add     rsp, 90h
0x18001be3d  pop     r15
0x18001be3f  pop     r14
0x18001be41  pop     r13
0x18001be43  pop     r12
0x18001be45  pop     rdi
0x18001be46  pop     rsi
0x18001be47  pop     rbx
0x18001be48  retn
```
