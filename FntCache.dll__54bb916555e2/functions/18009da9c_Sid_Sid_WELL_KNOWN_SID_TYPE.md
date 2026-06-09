# Sid::Sid(WELL_KNOWN_SID_TYPE)

- ea: `0x18009da9c`
- end: `0x18009db90`
- name: `??0Sid@@QEAA@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `244`
- prototype: `Sid *(Sid *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009d72c`

## callees

- `0x180004810`
- `0x1800217ac`
- `0x18002faf0`
- `0x18008fd38`
- `0x18009da9c`
- `0x1800a1558`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dad6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009dacc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009db70`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009dacc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009db70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Sid *__fastcall Sid::Sid(Sid *this, enum WELL_KNOWN_SID_TYPE a2)
{
  signed int LastError; // eax
  unsigned int v5; // edx
  __int64 v6; // rsi
  char *v7; // rdx
  unsigned __int64 v8; // rcx
  char *v9; // rax
  size_t v10; // rdi
  DWORD cbSid; // [rsp+50h] [rbp+18h] BYREF
  int v13; // [rsp+58h] [rbp+20h] BYREF

  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(this);
  cbSid = 0;
  if ( !CreateWellKnownSid(a2, 0, 0, &cbSid) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      Exception::Exception((Exception *)&v13, v5, LastError);
      LogAndThrow<OSException>(&v13, 4475219, 40);
    }
  }
  v6 = *((_QWORD *)this + 1);
  v7 = *(char **)this;
  v8 = v6 - *(_QWORD *)this;
  if ( cbSid >= v8 )
  {
    if ( cbSid <= v8 )
      goto LABEL_14;
    if ( (unsigned __int64)cbSid > *((_QWORD *)this + 2) - (_QWORD)v7 )
    {
      std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(this, cbSid);
      goto LABEL_14;
    }
    v10 = cbSid - v8;
    memset_0(*((void **)this + 1), 0, v10);
    v9 = (char *)(v10 + v6);
  }
  else
  {
    v9 = &v7[cbSid];
  }
  *((_QWORD *)this + 1) = v9;
LABEL_14:
  if ( !CreateWellKnownSid(a2, 0, *(PSID *)this, &cbSid) )
    OSException::ThrowLastError();
  return this;
}

```

## disassembly

```asm
0x18009da9c  mov     [rsp+arg_8], rbx
0x18009daa1  mov     [rsp+arg_0], rcx
0x18009daa6  push    rbp
0x18009daa7  push    rsi
0x18009daa8  push    rdi
0x18009daa9  sub     rsp, 20h
0x18009daad  mov     ebp, edx
0x18009daaf  mov     rbx, rcx
0x18009dab2  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18009dab7  nop
0x18009dab8  mov     [rsp+38h+cbSid], 0
0x18009dac0  lea     r9, [rsp+38h+cbSid]; cbSid
0x18009dac5  xor     r8d, r8d; pSid
0x18009dac8  xor     edx, edx; DomainSid
0x18009daca  mov     ecx, ebp; WellKnownSidType
0x18009dacc  call    cs:__imp_CreateWellKnownSid
0x18009dad2  test    eax, eax
0x18009dad4  jnz     short loc_18009DB15
0x18009dad6  call    cs:__imp_GetLastError
0x18009dadc  cmp     eax, 7Ah ; 'z'
0x18009dadf  jz      short loc_18009DB15
0x18009dae1  test    eax, eax
0x18009dae3  jg      short loc_18009DAE9
0x18009dae5  mov     edx, eax
0x18009dae7  jmp     short loc_18009DAF2
0x18009dae9  movzx   edx, ax
0x18009daec  or      edx, 80070000h; int
0x18009daf2  mov     r8d, eax; unsigned int
0x18009daf5  lea     rcx, [rsp+38h+arg_18]; this
0x18009dafa  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18009daff  mov     edx, 444953h
0x18009db04  mov     r8d, 28h ; '('
0x18009db0a  lea     rcx, [rsp+38h+arg_18]
0x18009db0f  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18009db15  mov     edi, [rsp+38h+cbSid]
0x18009db19  mov     rsi, [rbx+8]
0x18009db1d  mov     rdx, [rbx]
0x18009db20  mov     rcx, rsi
0x18009db23  sub     rcx, rdx
0x18009db26  cmp     rdi, rcx
0x18009db29  jnb     short loc_18009DB31
0x18009db2b  lea     rax, [rdx+rdi]
0x18009db2f  jmp     short loc_18009DB60
0x18009db31  jbe     short loc_18009DB64
0x18009db33  mov     rax, [rbx+10h]
0x18009db37  sub     rax, rdx
0x18009db3a  cmp     rdi, rax
0x18009db3d  jbe     short loc_18009DB4C
0x18009db3f  mov     rdx, rdi
0x18009db42  mov     rcx, rbx
0x18009db45  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18009db4a  jmp     short loc_18009DB64
0x18009db4c  sub     rdi, rcx
0x18009db4f  mov     r8, rdi; Size
0x18009db52  xor     edx, edx; Val
0x18009db54  mov     rcx, rsi; void *
0x18009db57  call    memset_0
0x18009db5c  lea     rax, [rdi+rsi]
0x18009db60  mov     [rbx+8], rax
0x18009db64  lea     r9, [rsp+38h+cbSid]; cbSid
0x18009db69  mov     r8, [rbx]; pSid
0x18009db6c  xor     edx, edx; DomainSid
0x18009db6e  mov     ecx, ebp; WellKnownSidType
0x18009db70  call    cs:__imp_CreateWellKnownSid
0x18009db76  test    eax, eax
0x18009db78  jnz     short loc_18009DB80
0x18009db7a  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x18009db80  mov     rax, rbx
0x18009db83  mov     rbx, [rsp+38h+arg_8]
0x18009db88  add     rsp, 20h
0x18009db8c  pop     rdi
0x18009db8d  pop     rsi
0x18009db8e  pop     rbp
0x18009db8f  retn
```
