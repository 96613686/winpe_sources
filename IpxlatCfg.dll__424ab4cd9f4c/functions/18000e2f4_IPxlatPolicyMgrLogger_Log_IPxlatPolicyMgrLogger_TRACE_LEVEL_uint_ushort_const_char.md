# IPxlatPolicyMgrLogger::Log(IPxlatPolicyMgrLogger::_TRACE_LEVEL,uint,ushort const *,char *)

- ea: `0x18000e2f4`
- end: `0x18000e436`
- name: `?Log@IPxlatPolicyMgrLogger@@AEAAXW4_TRACE_LEVEL@1@IPEBGPEAD@Z`
- size: `322`
- prototype: `ULONG __fastcall(__int64, int, int, const wchar_t *, va_list Args)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e43c`
- `0x18000e478`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180002a40`
- `0x18000e2f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000e40a`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000e40a`

## pseudocode

```c
ULONG __fastcall IPxlatPolicyMgrLogger::Log(__int64 a1, int a2, int a3, const wchar_t *a4, va_list Args)
{
  va_list v5; // rsi
  ULONG result; // eax
  __int64 v10; // rax
  EVENT_DESCRIPTOR v11; // xmm0
  ULONG v12; // r8d
  REGHANDLE v13; // rcx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE UserData[24]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h]
  wchar_t Buffer[520]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+4B0h] [rbp+3B0h] BYREF

  v18 = a3;
  v5 = Args;
  v16 = 0;
  memset(UserData, 0, sizeof(UserData));
  result = (unsigned int)memset_0(Buffer, 0, 0x402u);
  EventDescriptor = 0;
  if ( *(_QWORD *)a1 )
  {
    result = vsnwprintf(Buffer, 0x1FFu, a4, v5);
    if ( result < 0x200 )
    {
      if ( result == 511 )
        Buffer[511] = 0;
      *(_QWORD *)UserData = Buffer;
      v10 = -1;
      do
        ++v10;
      while ( Buffer[v10] );
      *(_QWORD *)&UserData[8] = (unsigned int)(2 * v10 + 2);
      if ( a2 )
      {
        v11 = *(EVENT_DESCRIPTOR *)(a1 + 24);
        v16 = 4;
        *(_QWORD *)&UserData[16] = &v18;
        v12 = 2;
      }
      else
      {
        v11 = *(EVENT_DESCRIPTOR *)(a1 + 8);
        v12 = 1;
      }
      v13 = *(_QWORD *)a1;
      EventDescriptor = v11;
      return EventWrite(v13, &EventDescriptor, v12, (PEVENT_DATA_DESCRIPTOR)UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e2f4  mov     [rsp-8+arg_8], rbx
0x18000e2f9  mov     [rsp-8+arg_10], r8d
0x18000e2fe  push    rbp
0x18000e2ff  push    rsi
0x18000e300  push    rdi
0x18000e301  push    r14
0x18000e303  push    r15
0x18000e305  lea     rbp, [rsp-370h]
0x18000e30d  sub     rsp, 470h
0x18000e314  mov     rax, cs:__security_cookie
0x18000e31b  xor     rax, rsp
0x18000e31e  mov     [rbp+390h+var_30], rax
0x18000e325  mov     rsi, [rbp+390h+Args]
0x18000e32c  mov     r14d, edx
0x18000e32f  mov     rbx, rcx
0x18000e332  xorps   xmm0, xmm0
0x18000e335  xor     eax, eax
0x18000e337  lea     rcx, [rsp+490h+Buffer]; void *
0x18000e33c  xor     r15d, r15d
0x18000e33f  mov     [rsp+490h+var_448], rax
0x18000e344  xor     edx, edx; Val
0x18000e346  mov     qword ptr [rsp+490h+UserData], r15
0x18000e34b  mov     r8d, 402h; Size
0x18000e351  mov     rdi, r9
0x18000e354  movups  xmmword ptr [rsp+490h+UserData+8], xmm0
0x18000e359  call    memset_0
0x18000e35e  xorps   xmm0, xmm0
0x18000e361  movups  xmmword ptr [rsp+490h+EventDescriptor.Id], xmm0
0x18000e366  cmp     [rbx], r15
0x18000e369  jz      loc_18000E410
0x18000e36f  mov     r8, rdi; Format
0x18000e372  lea     rcx, [rsp+490h+Buffer]; Buffer
0x18000e377  mov     edi, 1FFh
0x18000e37c  mov     r9, rsi; Args
0x18000e37f  mov     edx, edi; BufferCount
0x18000e381  call    _vsnwprintf
0x18000e386  test    eax, eax
0x18000e388  js      loc_18000E410
0x18000e38e  cmp     eax, edi
0x18000e390  ja      short loc_18000E410
0x18000e392  jnz     short loc_18000E39C
0x18000e394  mov     [rbp+390h+var_42], r15w
0x18000e39c  lea     rax, [rsp+490h+Buffer]
0x18000e3a1  mov     qword ptr [rsp+490h+UserData], rax
0x18000e3a6  lea     rcx, [rsp+490h+Buffer]
0x18000e3ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e3af  inc     rax
0x18000e3b2  cmp     [rcx+rax*2], r15w
0x18000e3b7  jnz     short loc_18000E3AF
0x18000e3b9  mov     dword ptr [rsp+490h+UserData+0Ch], r15d
0x18000e3be  lea     eax, ds:2[rax*2]
0x18000e3c5  mov     dword ptr [rsp+490h+UserData+8], eax
0x18000e3c9  test    r14d, r14d
0x18000e3cc  jnz     short loc_18000E3D8
0x18000e3ce  movups  xmm0, xmmword ptr [rbx+8]
0x18000e3d2  lea     r8d, [r14+1]
0x18000e3d6  jmp     short loc_18000E3F7
0x18000e3d8  movups  xmm0, xmmword ptr [rbx+18h]
0x18000e3dc  lea     rax, [rbp+390h+arg_10]
0x18000e3e3  mov     [rsp+490h+var_448], 4
0x18000e3ec  mov     qword ptr [rsp+490h+UserData+10h], rax
0x18000e3f1  mov     r8d, 2; UserDataCount
0x18000e3f7  mov     rcx, [rbx]; RegHandle
0x18000e3fa  lea     r9, [rsp+490h+UserData]; UserData
0x18000e3ff  lea     rdx, [rsp+490h+EventDescriptor]; EventDescriptor
0x18000e404  movdqu  xmmword ptr [rsp+490h+EventDescriptor.Id], xmm0
0x18000e40a  call    cs:__imp_EventWrite
0x18000e410  mov     rcx, [rbp+390h+var_30]
0x18000e417  xor     rcx, rsp; StackCookie
0x18000e41a  call    __security_check_cookie
0x18000e41f  mov     rbx, [rsp+490h+arg_8]
0x18000e427  add     rsp, 470h
0x18000e42e  pop     r15
0x18000e430  pop     r14
0x18000e432  pop     rdi
0x18000e433  pop     rsi
0x18000e434  pop     rbp
0x18000e435  retn
```
