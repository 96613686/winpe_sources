# AppEnumeratorImpl::ScanForPackagesOnVolume(void)

- ea: `0x180002f40`
- end: `0x180003206`
- name: `?ScanForPackagesOnVolume@AppEnumeratorImpl@@AEAAXXZ`
- size: `710`
- prototype: `void __fastcall(AppEnumeratorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180002f40`
- `0x180003210`
- `0x1800a6cd8`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x18000313c`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180003146`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x18000313c`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x180003146`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003086`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180003086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800031e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800031f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ff3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800031e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800031f9`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18000305d`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18000305d`

## pseudocode

```c
void __fastcall AppEnumeratorImpl::ScanForPackagesOnVolume(AppEnumeratorImpl *this)
{
  AppEnumeratorImpl *v1; // r14
  _BYTE *v2; // rcx
  __int64 v3; // rcx
  int v4; // eax
  unsigned __int16 *v5; // rsi
  int (__fastcall *v6)(unsigned __int16 *, char *); // rdi
  unsigned __int16 *v7; // rdi
  int (__fastcall *v8)(unsigned __int16 *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  int FilenameInAppContainerStorage; // ebx
  unsigned __int16 *v11; // r12
  __int64 v12; // rax
  char *v13; // r8
  unsigned __int16 *v14; // r13
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int16 *v17; // r14
  unsigned __int16 *v18; // r15
  unsigned __int16 *i; // rbx
  int v20; // edi
  int v21; // esi
  int v22; // eax
  unsigned __int16 *v23; // [rsp+20h] [rbp-38h]
  void **pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  int v25; // [rsp+30h] [rbp-28h]
  __int128 v26; // [rsp+38h] [rbp-20h]
  HSTRING string; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v29; // [rsp+B0h] [rbp+58h] BYREF
  PSID pSid; // [rsp+B8h] [rbp+60h] BYREF

  v1 = this;
  v2 = (char *)this + 32;
  while ( *v2 )
  {
    v3 = *((_QWORD *)v1 + 5);
    if ( v3 )
    {
      *((_QWORD *)v1 + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 3) + 48LL))(
           *((_QWORD *)v1 + 3),
           (__int64)v1 + 40);
    if ( v4 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v25 = v4;
      v26 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    v29 = 0;
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)v1 + 5) + 48LL))(*((_QWORD *)v1 + 5), &v29) < 0 )
      goto LABEL_30;
    v5 = v29;
    v6 = *(int (__fastcall **)(unsigned __int16 *, char *))(*(_QWORD *)v29 + 48LL);
    WindowsDeleteString(*((HSTRING *)v1 + 6));
    *((_QWORD *)v1 + 6) = 0;
    if ( v6(v5, (char *)v1 + 48) < 0 )
      goto LABEL_30;
    string = 0;
    v7 = v29;
    v8 = *(int (__fastcall **)(unsigned __int16 *, HSTRING *))(*(_QWORD *)v29 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v8(v7, &string) < 0
      || (pSid = 0,
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
          (int)DeriveAppContainerSidFromAppContainerName(StringRawBuffer, &pSid) < 0) )
    {
      WindowsDeleteString(string);
      string = 0;
LABEL_30:
      if ( v29 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_28;
    }
    FilenameInAppContainerStorage = GetFilenameInAppContainerStorage((unsigned __int16 *)v1 + 28, 0x104u, pSid, 0);
    FreeSid(pSid);
    WindowsDeleteString(string);
    string = 0;
    if ( v29 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 16LL))(v29);
    if ( FilenameInAppContainerStorage >= 0 )
    {
      v11 = (unsigned __int16 *)((char *)v1 + 56);
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = (char *)v1 + 2 * v12 + 56;
      v23 = (unsigned __int16 *)v13;
      v14 = *(unsigned __int16 **)v1;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      v16 = (2 * v15) >> 1;
      if ( (v13 - (char *)v11) >> 1 >= v16 )
      {
        v17 = &v14[v15];
        v29 = (unsigned __int16 *)&v13[-2 * v16];
LABEL_20:
        v18 = v11;
        for ( i = v14; i != v17; ++i )
        {
          v20 = *v18;
          v21 = toupper(*i);
          if ( toupper(v20) != v21 )
          {
            if ( v11 != v29 )
            {
              ++v11;
              goto LABEL_20;
            }
            goto LABEL_27;
          }
          ++v18;
        }
        if ( v11 != v23 )
          return;
LABEL_27:
        v1 = this;
      }
    }
LABEL_28:
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 3) + 64LL))(
            *((_QWORD *)v1 + 3),
            (__int64)v1 + 32);
    v2 = (char *)v1 + 32;
    if ( v22 < 0 )
    {
      pExceptionObject = &_com_error::`vftable';
      v25 = v22;
      v26 = 0;
      throw (_com_error *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180002f40  mov     [rsp-40h+arg_0], rcx
0x180002f45  push    rbp
0x180002f46  push    rbx
0x180002f47  push    rsi
0x180002f48  push    rdi
0x180002f49  push    r12
0x180002f4b  push    r13
0x180002f4d  push    r14
0x180002f4f  push    r15
0x180002f51  mov     rbp, rsp
0x180002f54  sub     rsp, 58h
0x180002f58  mov     r14, rcx
0x180002f5b  add     rcx, 20h ; ' '
0x180002f5f  xor     r15d, r15d
0x180002f62  cmp     byte ptr [rcx], 0
0x180002f65  jz      loc_1800031D2
0x180002f6b  mov     rcx, [r14+28h]
0x180002f6f  test    rcx, rcx
0x180002f72  jz      short loc_180002F85
0x180002f74  mov     [r14+28h], r15
0x180002f78  mov     rax, [rcx]
0x180002f7b  mov     rax, [rax+10h]
0x180002f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f84  nop
0x180002f85  mov     rcx, [r14+18h]
0x180002f89  mov     rax, [rcx]
0x180002f8c  lea     rdx, [r14+28h]
0x180002f90  mov     rax, [rax+30h]
0x180002f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f99  test    eax, eax
0x180002f9b  jns     short loc_180002FC4
0x180002f9d  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180002fa4  mov     [rbp+pExceptionObject], rcx
0x180002fa8  mov     [rbp+var_28], eax
0x180002fab  xorps   xmm0, xmm0
0x180002fae  movdqu  [rbp+var_20], xmm0
0x180002fb3  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002fba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002fbe  call    _CxxThrowException_0
0x180002fc4  mov     [rbp+arg_10], r15
0x180002fc8  mov     rcx, [r14+28h]
0x180002fcc  mov     rax, [rcx]
0x180002fcf  lea     rdx, [rbp+arg_10]
0x180002fd3  mov     rax, [rax+30h]
0x180002fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fdc  test    eax, eax
0x180002fde  js      loc_1800031BA
0x180002fe4  mov     rsi, [rbp+arg_10]
0x180002fe8  mov     rax, [rsi]
0x180002feb  mov     rdi, [rax+30h]
0x180002fef  mov     rcx, [r14+30h]; string
0x180002ff3  call    cs:__imp_WindowsDeleteString
0x180002ff9  mov     [r14+30h], r15
0x180002ffd  lea     rdx, [r14+30h]
0x180003001  mov     rcx, rsi
0x180003004  mov     rax, rdi
0x180003007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000300c  test    eax, eax
0x18000300e  js      loc_1800031F3
0x180003014  mov     [rbp+string], r15
0x180003018  mov     rdi, [rbp+arg_10]
0x18000301c  mov     rax, [rdi]
0x18000301f  mov     rbx, [rax+68h]
0x180003023  xor     ecx, ecx; string
0x180003025  call    cs:__imp_WindowsDeleteString
0x18000302b  mov     [rbp+string], r15
0x18000302f  lea     rdx, [rbp+string]
0x180003033  mov     rcx, rdi
0x180003036  mov     rax, rbx
0x180003039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303e  test    eax, eax
0x180003040  js      loc_1800031F5
0x180003046  mov     [rbp+pSid], r15
0x18000304a  xor     edx, edx; length
0x18000304c  mov     rcx, [rbp+string]; string
0x180003050  call    cs:__imp_WindowsGetStringRawBuffer
0x180003056  lea     rdx, [rbp+pSid]
0x18000305a  mov     rcx, rax
0x18000305d  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x180003063  test    eax, eax
0x180003065  js      loc_1800031E3
0x18000306b  lea     rcx, [r14+38h]; unsigned __int16 *
0x18000306f  xor     r9d, r9d; unsigned __int16 *
0x180003072  mov     r8, [rbp+pSid]; Sid
0x180003076  mov     edx, 104h; unsigned int
0x18000307b  call    ?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ; GetFilenameInAppContainerStorage(ushort *,uint,void *,ushort const *,...)
0x180003080  mov     ebx, eax
0x180003082  mov     rcx, [rbp+pSid]; pSid
0x180003086  call    cs:__imp_FreeSid
0x18000308c  nop
0x18000308d  mov     rcx, [rbp+string]; string
0x180003091  call    cs:__imp_WindowsDeleteString
0x180003097  mov     [rbp+string], r15
0x18000309b  mov     rcx, [rbp+arg_10]
0x18000309f  test    rcx, rcx
0x1800030a2  jz      short loc_1800030B1
0x1800030a4  mov     rdx, [rcx]
0x1800030a7  mov     rax, [rdx+10h]
0x1800030ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b0  nop
0x1800030b1  test    ebx, ebx
0x1800030b3  js      loc_180003173
0x1800030b9  lea     r12, [r14+38h]
0x1800030bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800030c4  inc     rax
0x1800030c7  cmp     word ptr [r12+rax*2], 0
0x1800030cd  jnz     short loc_1800030C4
0x1800030cf  add     rax, 1Ch
0x1800030d3  lea     r8, [r14+rax*2]
0x1800030d7  mov     [rbp+var_38], r8
0x1800030db  mov     r13, [r14]
0x1800030de  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800030e5  nop     word ptr [rax+rax+00000000h]
0x1800030f0  lea     rax, [rax+1]
0x1800030f4  cmp     word ptr [r13+rax*2+0], 0
0x1800030fb  jnz     short loc_1800030F0
0x1800030fd  lea     rdx, [rax+rax]
0x180003101  mov     rcx, rdx
0x180003104  sar     rcx, 1
0x180003107  mov     rax, r8
0x18000310a  sub     rax, r12
0x18000310d  sar     rax, 1
0x180003110  cmp     rax, rcx
0x180003113  jl      short loc_180003173
0x180003115  lea     r14, [rdx+r13]
0x180003119  lea     rax, [rcx+rcx]
0x18000311d  mov     rcx, r8
0x180003120  sub     rcx, rax
0x180003123  mov     [rbp+arg_10], rcx
0x180003127  mov     r15, r12
0x18000312a  mov     rbx, r13
0x18000312d  nop     dword ptr [rax]
0x180003130  cmp     rbx, r14
0x180003133  jz      short loc_180003166
0x180003135  movzx   ecx, word ptr [rbx]; C
0x180003138  movzx   edi, word ptr [r15]
0x18000313c  call    cs:__imp_toupper
0x180003142  mov     esi, eax
0x180003144  mov     ecx, edi; C
0x180003146  call    cs:__imp_toupper
0x18000314c  cmp     eax, esi
0x18000314e  jnz     short loc_18000315A
0x180003150  add     r15, 2
0x180003154  add     rbx, 2
0x180003158  jmp     short loc_180003130
0x18000315a  cmp     r12, [rbp+arg_10]
0x18000315e  jz      short loc_18000316C
0x180003160  add     r12, 2
0x180003164  jmp     short loc_180003127
0x180003166  cmp     r12, [rbp+var_38]
0x18000316a  jnz     short loc_1800031D2
0x18000316c  xor     r15d, r15d
0x18000316f  mov     r14, [rbp+arg_0]
0x180003173  mov     rcx, [r14+18h]
0x180003177  mov     rax, [rcx]
0x18000317a  lea     rdx, [r14+20h]
0x18000317e  mov     rax, [rax+40h]
0x180003182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003187  test    eax, eax
0x180003189  lea     rcx, [r14+20h]
0x18000318d  jns     loc_180002F62
0x180003193  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000319a  mov     [rbp+pExceptionObject], rcx
0x18000319e  mov     [rbp+var_28], eax
0x1800031a1  xorps   xmm0, xmm0
0x1800031a4  movdqu  [rbp+var_20], xmm0
0x1800031a9  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800031b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800031b4  call    _CxxThrowException_0
0x1800031ba  mov     rcx, [rbp+arg_10]
0x1800031be  test    rcx, rcx
0x1800031c1  jz      short loc_1800031D0
0x1800031c3  mov     rax, [rcx]
0x1800031c6  mov     rax, [rax+10h]
0x1800031ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cf  nop
0x1800031d0  jmp     short loc_180003173
0x1800031d2  add     rsp, 58h
0x1800031d6  pop     r15
0x1800031d8  pop     r14
0x1800031da  pop     r13
0x1800031dc  pop     r12
0x1800031de  pop     rdi
0x1800031df  pop     rsi
0x1800031e0  pop     rbx
0x1800031e1  pop     rbp
0x1800031e2  retn
0x1800031e3  mov     rcx, [rbp+string]; string
0x1800031e7  call    cs:__imp_WindowsDeleteString
0x1800031ed  mov     [rbp+string], r15
0x1800031f1  jmp     short loc_1800031BA
0x1800031f3  jmp     short loc_1800031BA
0x1800031f5  mov     rcx, [rbp+string]; string
0x1800031f9  call    cs:__imp_WindowsDeleteString
0x1800031ff  mov     [rbp+string], r15
0x180003203  jmp     short loc_1800031BA
```
