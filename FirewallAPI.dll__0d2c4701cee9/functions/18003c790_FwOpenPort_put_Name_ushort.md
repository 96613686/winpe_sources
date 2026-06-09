# FwOpenPort::put_Name(ushort *)

- ea: `0x18003c790`
- end: `0x18003c936`
- name: `?put_Name@FwOpenPort@@UEAAJPEAG@Z`
- size: `422`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003c790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c7d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c7d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c8e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c8e4`
- `fwbase!FwReportReturnError` at `0x18003c8d4`
- `fwbase!FwReportReturnError` at `0x18003c8fd`
- `fwbase!FwReportReturnError` at `0x18003c8d4`
- `fwbase!FwReportReturnError` at `0x18003c8fd`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c801`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c801`

## string_xrefs

- `0x18003c8cd`: `FwOpenPort::put_Name`
- `0x18003c8f6`: `FwOpenPort::put_Name`

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
0x18003c790  mov     [rsp+arg_10], rbx
0x18003c795  mov     [rsp+arg_18], rbp
0x18003c79a  push    rsi
0x18003c79b  push    rdi
0x18003c79c  push    r14
0x18003c79e  sub     rsp, 230h
0x18003c7a5  mov     rax, cs:__security_cookie
0x18003c7ac  xor     rax, rsp
0x18003c7af  mov     [rsp+248h+var_28], rax
0x18003c7b7  mov     r14, rdx
0x18003c7ba  mov     rdi, rcx
0x18003c7bd  xor     edx, edx; Val
0x18003c7bf  lea     rcx, [rsp+248h+var_228]; void *
0x18003c7c4  mov     r8d, 1F8h; Size
0x18003c7ca  call    memset_0
0x18003c7cf  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c7d3  call    cs:__imp_EnterCriticalSection
0x18003c7da  nop     dword ptr [rax+rax+00h]
0x18003c7df  cmp     dword ptr [rdi+50h], 0
0x18003c7e3  jz      short loc_18003C7F1
0x18003c7e5  mov     ebx, 80070005h
0x18003c7ea  mov     edx, ebx
0x18003c7ec  jmp     loc_18003C8CD
0x18003c7f1  lea     rsi, [rdi+48h]
0x18003c7f5  cmp     qword ptr [rsi], 0
0x18003c7f9  jnz     short loc_18003C817
0x18003c7fb  mov     edx, [rdi+40h]
0x18003c7fe  mov     rcx, rsi
0x18003c801  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c808  nop     dword ptr [rax+rax+00h]
0x18003c80d  mov     ebx, eax
0x18003c80f  test    eax, eax
0x18003c811  js      loc_18003C8CB
0x18003c817  mov     rax, [rsi]
0x18003c81a  lea     rdx, [rsp+248h+var_228]
0x18003c81f  mov     ecx, 3
0x18003c824  lea     r8d, [rcx+7Dh]
0x18003c828  movups  xmm0, xmmword ptr [rax]
0x18003c82b  movups  xmmword ptr [rdx], xmm0
0x18003c82e  movups  xmm1, xmmword ptr [rax+10h]
0x18003c832  movups  xmmword ptr [rdx+10h], xmm1
0x18003c836  movups  xmm0, xmmword ptr [rax+20h]
0x18003c83a  movups  xmmword ptr [rdx+20h], xmm0
0x18003c83e  movups  xmm1, xmmword ptr [rax+30h]
0x18003c842  movups  xmmword ptr [rdx+30h], xmm1
0x18003c846  movups  xmm0, xmmword ptr [rax+40h]
0x18003c84a  movups  xmmword ptr [rdx+40h], xmm0
0x18003c84e  movups  xmm1, xmmword ptr [rax+50h]
0x18003c852  movups  xmmword ptr [rdx+50h], xmm1
0x18003c856  movups  xmm0, xmmword ptr [rax+60h]
0x18003c85a  movups  xmmword ptr [rdx+60h], xmm0
0x18003c85e  movups  xmm1, xmmword ptr [rax+70h]
0x18003c862  add     rax, r8
0x18003c865  movups  xmmword ptr [rdx+70h], xmm1
0x18003c869  add     rdx, r8
0x18003c86c  sub     rcx, 1
0x18003c870  jnz     short loc_18003C828
0x18003c872  movups  xmm0, xmmword ptr [rax]
0x18003c875  mov     r8, [rsi]; struct _tag_FW_RULE *
0x18003c878  mov     rcx, rdi; this
0x18003c87b  movups  xmmword ptr [rdx], xmm0
0x18003c87e  movups  xmm1, xmmword ptr [rax+10h]
0x18003c882  movups  xmmword ptr [rdx+10h], xmm1
0x18003c886  movups  xmm0, xmmword ptr [rax+20h]
0x18003c88a  movups  xmmword ptr [rdx+20h], xmm0
0x18003c88e  movups  xmm1, xmmword ptr [rax+30h]
0x18003c892  movups  xmmword ptr [rdx+30h], xmm1
0x18003c896  movups  xmm0, xmmword ptr [rax+40h]
0x18003c89a  movups  xmmword ptr [rdx+40h], xmm0
0x18003c89e  movups  xmm1, xmmword ptr [rax+50h]
0x18003c8a2  movups  xmmword ptr [rdx+50h], xmm1
0x18003c8a6  movups  xmm0, xmmword ptr [rax+60h]
0x18003c8aa  movups  xmmword ptr [rdx+60h], xmm0
0x18003c8ae  mov     rax, [rax+70h]
0x18003c8b2  mov     [rdx+70h], rax
0x18003c8b6  lea     rdx, [rsp+248h+var_228]; struct _tag_FW_RULE *
0x18003c8bb  mov     [rsp+248h+var_210], r14
0x18003c8c0  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003c8c5  mov     ebx, eax
0x18003c8c7  test    eax, eax
0x18003c8c9  jns     short loc_18003C8E0
0x18003c8cb  mov     edx, eax
0x18003c8cd  lea     rcx, aFwopenportPutN; "FwOpenPort::put_Name"
0x18003c8d4  call    cs:__imp_FwReportReturnError
0x18003c8db  nop     dword ptr [rax+rax+00h]
0x18003c8e0  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003c8e4  call    cs:__imp_LeaveCriticalSection
0x18003c8eb  nop     dword ptr [rax+rax+00h]
0x18003c8f0  test    ebx, ebx
0x18003c8f2  jns     short loc_18003C90B
0x18003c8f4  mov     edx, ebx
0x18003c8f6  lea     rcx, aFwopenportPutN; "FwOpenPort::put_Name"
0x18003c8fd  call    cs:__imp_FwReportReturnError
0x18003c904  nop     dword ptr [rax+rax+00h]
0x18003c909  mov     ebx, eax
0x18003c90b  mov     eax, ebx
0x18003c90d  mov     rcx, [rsp+248h+var_28]
0x18003c915  xor     rcx, rsp; StackCookie
0x18003c918  call    __security_check_cookie
0x18003c91d  lea     r11, [rsp+248h+var_18]
0x18003c925  mov     rbx, [r11+30h]
0x18003c929  mov     rbp, [r11+38h]
0x18003c92d  mov     rsp, r11
0x18003c930  pop     r14
0x18003c932  pop     rdi
0x18003c933  pop     rsi
0x18003c934  retn
```
