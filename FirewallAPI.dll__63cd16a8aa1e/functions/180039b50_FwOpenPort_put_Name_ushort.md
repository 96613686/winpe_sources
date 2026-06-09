# FwOpenPort::put_Name(ushort *)

- ea: `0x180039b50`
- end: `0x180039cd7`
- name: `?put_Name@FwOpenPort@@UEAAJPEAG@Z`
- size: `391`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x180039b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039b93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039b93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039c92`
- `fwbase!FwReportReturnError` at `0x180039c88`
- `fwbase!FwReportReturnError` at `0x180039ca5`
- `fwbase!FwReportReturnError` at `0x180039c88`
- `fwbase!FwReportReturnError` at `0x180039ca5`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039bbb`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039bbb`

## string_xrefs

- `0x180039c81`: `FwOpenPort::put_Name`
- `0x180039c9e`: `FwOpenPort::put_Name`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Name(FwOpenPort *this, unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  struct _tag_FW_RULE **v6; // rsi
  int DefaultOpenPortRule; // eax
  struct _tag_FW_RULE *v8; // rax
  _OWORD *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  struct _tag_FW_RULE *v12; // r8
  _BYTE v14[24]; // [rsp+20h] [rbp-228h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-210h]

  memset_0(v14, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 20) )
  {
    v4 = -2147024891;
    v5 = 2147942405LL;
  }
  else
  {
    v6 = (struct _tag_FW_RULE **)((char *)this + 72);
    if ( *((_QWORD *)this + 9)
      || (DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16)),
          v4 = DefaultOpenPortRule,
          DefaultOpenPortRule >= 0) )
    {
      v8 = *v6;
      v9 = v14;
      v10 = 3;
      do
      {
        *v9 = *(_OWORD *)v8;
        v9[1] = *((_OWORD *)v8 + 1);
        v9[2] = *((_OWORD *)v8 + 2);
        v9[3] = *((_OWORD *)v8 + 3);
        v9[4] = *((_OWORD *)v8 + 4);
        v9[5] = *((_OWORD *)v8 + 5);
        v9[6] = *((_OWORD *)v8 + 6);
        v11 = *((_OWORD *)v8 + 7);
        v8 = (struct _tag_FW_RULE *)((char *)v8 + 128);
        v9[7] = v11;
        v9 += 8;
        --v10;
      }
      while ( v10 );
      v12 = *v6;
      *v9 = *(_OWORD *)v8;
      v9[1] = *((_OWORD *)v8 + 1);
      v9[2] = *((_OWORD *)v8 + 2);
      v9[3] = *((_OWORD *)v8 + 3);
      v9[4] = *((_OWORD *)v8 + 4);
      v9[5] = *((_OWORD *)v8 + 5);
      v9[6] = *((_OWORD *)v8 + 6);
      *((_QWORD *)v9 + 14) = *((_QWORD *)v8 + 14);
      v15 = a2;
      DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v14, v12);
      v4 = DefaultOpenPortRule;
      if ( DefaultOpenPortRule >= 0 )
        goto LABEL_10;
    }
    v5 = (unsigned int)DefaultOpenPortRule;
  }
  FwReportReturnError("FwOpenPort::put_Name", v5);
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Name", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039b50  mov     [rsp+arg_10], rbx
0x180039b55  mov     [rsp+arg_18], rbp
0x180039b5a  push    rsi
0x180039b5b  push    rdi
0x180039b5c  push    r14
0x180039b5e  sub     rsp, 230h
0x180039b65  mov     rax, cs:__security_cookie
0x180039b6c  xor     rax, rsp
0x180039b6f  mov     [rsp+248h+var_28], rax
0x180039b77  mov     r14, rdx
0x180039b7a  mov     rdi, rcx
0x180039b7d  xor     edx, edx; Val
0x180039b7f  lea     rcx, [rsp+248h+var_228]; void *
0x180039b84  mov     r8d, 1F8h; Size
0x180039b8a  call    memset_0
0x180039b8f  lea     rcx, [rdi+10h]; lpCriticalSection
0x180039b93  call    cs:__imp_EnterCriticalSection
0x180039b99  cmp     dword ptr [rdi+50h], 0
0x180039b9d  jz      short loc_180039BAB
0x180039b9f  mov     ebx, 80070005h
0x180039ba4  mov     edx, ebx
0x180039ba6  jmp     loc_180039C81
0x180039bab  lea     rsi, [rdi+48h]
0x180039baf  cmp     qword ptr [rsi], 0
0x180039bb3  jnz     short loc_180039BCB
0x180039bb5  mov     edx, [rdi+40h]
0x180039bb8  mov     rcx, rsi
0x180039bbb  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180039bc1  mov     ebx, eax
0x180039bc3  test    eax, eax
0x180039bc5  js      loc_180039C7F
0x180039bcb  mov     rax, [rsi]
0x180039bce  lea     rdx, [rsp+248h+var_228]
0x180039bd3  mov     ecx, 3
0x180039bd8  lea     r8d, [rcx+7Dh]
0x180039bdc  movups  xmm0, xmmword ptr [rax]
0x180039bdf  movups  xmmword ptr [rdx], xmm0
0x180039be2  movups  xmm1, xmmword ptr [rax+10h]
0x180039be6  movups  xmmword ptr [rdx+10h], xmm1
0x180039bea  movups  xmm0, xmmword ptr [rax+20h]
0x180039bee  movups  xmmword ptr [rdx+20h], xmm0
0x180039bf2  movups  xmm1, xmmword ptr [rax+30h]
0x180039bf6  movups  xmmword ptr [rdx+30h], xmm1
0x180039bfa  movups  xmm0, xmmword ptr [rax+40h]
0x180039bfe  movups  xmmword ptr [rdx+40h], xmm0
0x180039c02  movups  xmm1, xmmword ptr [rax+50h]
0x180039c06  movups  xmmword ptr [rdx+50h], xmm1
0x180039c0a  movups  xmm0, xmmword ptr [rax+60h]
0x180039c0e  movups  xmmword ptr [rdx+60h], xmm0
0x180039c12  movups  xmm1, xmmword ptr [rax+70h]
0x180039c16  add     rax, r8
0x180039c19  movups  xmmword ptr [rdx+70h], xmm1
0x180039c1d  add     rdx, r8
0x180039c20  sub     rcx, 1
0x180039c24  jnz     short loc_180039BDC
0x180039c26  movups  xmm0, xmmword ptr [rax]
0x180039c29  mov     r8, [rsi]; struct _tag_FW_RULE *
0x180039c2c  mov     rcx, rdi; this
0x180039c2f  movups  xmmword ptr [rdx], xmm0
0x180039c32  movups  xmm1, xmmword ptr [rax+10h]
0x180039c36  movups  xmmword ptr [rdx+10h], xmm1
0x180039c3a  movups  xmm0, xmmword ptr [rax+20h]
0x180039c3e  movups  xmmword ptr [rdx+20h], xmm0
0x180039c42  movups  xmm1, xmmword ptr [rax+30h]
0x180039c46  movups  xmmword ptr [rdx+30h], xmm1
0x180039c4a  movups  xmm0, xmmword ptr [rax+40h]
0x180039c4e  movups  xmmword ptr [rdx+40h], xmm0
0x180039c52  movups  xmm1, xmmword ptr [rax+50h]
0x180039c56  movups  xmmword ptr [rdx+50h], xmm1
0x180039c5a  movups  xmm0, xmmword ptr [rax+60h]
0x180039c5e  movups  xmmword ptr [rdx+60h], xmm0
0x180039c62  mov     rax, [rax+70h]
0x180039c66  mov     [rdx+70h], rax
0x180039c6a  lea     rdx, [rsp+248h+var_228]; struct _tag_FW_RULE *
0x180039c6f  mov     [rsp+248h+var_210], r14
0x180039c74  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180039c79  mov     ebx, eax
0x180039c7b  test    eax, eax
0x180039c7d  jns     short loc_180039C8E
0x180039c7f  mov     edx, eax
0x180039c81  lea     rcx, aFwopenportPutN; "FwOpenPort::put_Name"
0x180039c88  call    cs:__imp_FwReportReturnError
0x180039c8e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180039c92  call    cs:__imp_LeaveCriticalSection
0x180039c98  test    ebx, ebx
0x180039c9a  jns     short loc_180039CAD
0x180039c9c  mov     edx, ebx
0x180039c9e  lea     rcx, aFwopenportPutN; "FwOpenPort::put_Name"
0x180039ca5  call    cs:__imp_FwReportReturnError
0x180039cab  mov     ebx, eax
0x180039cad  mov     eax, ebx
0x180039caf  mov     rcx, [rsp+248h+var_28]
0x180039cb7  xor     rcx, rsp; StackCookie
0x180039cba  call    __security_check_cookie
0x180039cbf  lea     r11, [rsp+248h+var_18]
0x180039cc7  mov     rbx, [r11+30h]
0x180039ccb  mov     rbp, [r11+38h]
0x180039ccf  mov     rsp, r11
0x180039cd2  pop     r14
0x180039cd4  pop     rdi
0x180039cd5  pop     rsi
0x180039cd6  retn
```
