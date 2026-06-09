# Sid::CopySidFrom(void *)

- ea: `0x18008fb80`
- end: `0x18008fc11`
- name: `?CopySidFrom@Sid@@AEAAXPEAX@Z`
- size: `145`
- prototype: `void(Sid *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008fb04`
- `0x18009dca0`

## callees

- `0x18008fb80`
- `0x18008fd38`
- `0x1800a1558`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008fb94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008fb94`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008fbd2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008fbd2`

## pseudocode

```c
void __fastcall Sid::CopySidFrom(Sid *this, void *a2)
{
  DWORD LengthSid; // eax
  __int64 v5; // rsi
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  DWORD v8; // r14d
  size_t v9; // rbx

  LengthSid = GetLengthSid(a2);
  v5 = *((_QWORD *)this + 1);
  v6 = *(_QWORD *)this;
  v7 = v5 - *(_QWORD *)this;
  v8 = LengthSid;
  if ( LengthSid < v7 )
  {
    *((_QWORD *)this + 1) = LengthSid + v6;
  }
  else if ( LengthSid > v7 )
  {
    if ( LengthSid <= (unsigned __int64)(*((_QWORD *)this + 2) - v6) )
    {
      v9 = LengthSid - v7;
      memset_0(*((void **)this + 1), 0, v9);
      *((_QWORD *)this + 1) = v9 + v5;
    }
    else
    {
      std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(this, LengthSid);
    }
  }
  if ( !CopySid(v8, *(PSID *)this, a2) )
    OSException::ThrowLastError();
}

```

## disassembly

```asm
0x18008fb80  push    rbx
0x18008fb82  push    rbp
0x18008fb83  push    rsi
0x18008fb84  push    rdi
0x18008fb85  push    r14
0x18008fb87  sub     rsp, 20h
0x18008fb8b  mov     rdi, rcx
0x18008fb8e  mov     rbp, rdx
0x18008fb91  mov     rcx, rdx; pSid
0x18008fb94  call    cs:__imp_GetLengthSid
0x18008fb9a  mov     rsi, [rdi+8]
0x18008fb9e  mov     r8, [rdi]
0x18008fba1  mov     rcx, rsi
0x18008fba4  sub     rcx, r8
0x18008fba7  mov     r14d, eax
0x18008fbaa  mov     ebx, eax
0x18008fbac  cmp     r14, rcx
0x18008fbaf  jb      short loc_18008FBE7
0x18008fbb1  jbe     short loc_18008FBC9
0x18008fbb3  mov     rax, [rdi+10h]
0x18008fbb7  sub     rax, r8
0x18008fbba  cmp     rbx, rax
0x18008fbbd  jbe     short loc_18008FBF1
0x18008fbbf  mov     edx, ebx
0x18008fbc1  mov     rcx, rdi
0x18008fbc4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008fbc9  mov     rdx, [rdi]; pDestinationSid
0x18008fbcc  mov     r8, rbp; pSourceSid
0x18008fbcf  mov     ecx, r14d; nDestinationSidLength
0x18008fbd2  call    cs:__imp_CopySid
0x18008fbd8  test    eax, eax
0x18008fbda  jz      short loc_18008FC0B
0x18008fbdc  add     rsp, 20h
0x18008fbe0  pop     r14
0x18008fbe2  pop     rdi
0x18008fbe3  pop     rsi
0x18008fbe4  pop     rbp
0x18008fbe5  pop     rbx
0x18008fbe6  retn
0x18008fbe7  lea     rcx, [r14+r8]
0x18008fbeb  mov     [rdi+8], rcx
0x18008fbef  jmp     short loc_18008FBC9
0x18008fbf1  sub     rbx, rcx
0x18008fbf4  xor     edx, edx; Val
0x18008fbf6  mov     r8, rbx; Size
0x18008fbf9  mov     rcx, rsi; void *
0x18008fbfc  call    memset_0
0x18008fc01  lea     rax, [rbx+rsi]
0x18008fc05  mov     [rdi+8], rax
0x18008fc09  jmp     short loc_18008FBC9
0x18008fc0b  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
