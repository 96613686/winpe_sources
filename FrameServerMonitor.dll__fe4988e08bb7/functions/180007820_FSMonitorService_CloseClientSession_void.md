# FSMonitorService::CloseClientSession(void *)

- ea: `0x180007820`
- end: `0x180007a6f`
- name: `?CloseClientSession@FSMonitorService@@UEAAJPEAX@Z`
- size: `591`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180007820`
- `0x18000985c`
- `0x18000d778`
- `0x18004bf5c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000783b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000783b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a56`

## pseudocode

```c
__int64 __fastcall FSMonitorService::CloseClientSession(FSMonitorService *this, void *a2)
{
  unsigned int v4; // r13d
  int v5; // esi
  char v6; // r14
  __int64 i; // rbp
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // r9
  __int64 *v14; // rcx
  __int64 v15; // r14
  unsigned int v16; // edx
  __int64 v17; // rdx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = *((_DWORD *)this + 38);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 49, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, a2);
  if ( *((_DWORD *)this + 23) == 1 )
  {
    v5 = 0;
    v6 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v4 )
        goto LABEL_21;
      v8 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
      if ( (*(unsigned __int8 (__fastcall **)(__int64, void *))(*(_QWORD *)v8 + 64LL))(v8, a2) )
        break;
    }
    _mm_lfence();
    v9 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
    v5 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v9 + 88LL))(v9, a2);
    v10 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10) )
    {
      _mm_lfence();
      v11 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 152LL))(v11);
      v12 = *((_DWORD *)this + 38);
      if ( v12 > (unsigned int)i )
      {
        _mm_lfence();
        if ( v12 )
        {
          if ( (unsigned int)i <= v12 - 1 )
          {
            v13 = *((_QWORD *)this + 18);
            v14 = (__int64 *)(v13 + 8 * i);
            v15 = *v14;
            v16 = v12 - i - 1;
            if ( v16 )
              memmove_0(v14, (const void *)(v13 + 8LL * (unsigned int)(i + 1)), 8LL * v16);
            --*((_DWORD *)this + 38);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
        }
      }
    }
    v6 = 1;
    if ( v5 >= 0 )
    {
LABEL_21:
      FSMonitorService::InternalStartIdleTimer(this);
      if ( !v6 )
      {
        v5 = -1072875819;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
            this,
            -1072875819);
      }
      goto LABEL_24;
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v5);
    if ( v5 != -1072875819 )
      goto LABEL_28;
LABEL_24:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
      goto LABEL_31;
    v17 = 54;
    goto LABEL_30;
  }
  v5 = -1072873851;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      this,
      -1072873851);
LABEL_28:
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
  {
    v17 = 53;
LABEL_30:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v17, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v5);
  }
LABEL_31:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007820  push    rbx
0x180007822  push    rbp
0x180007823  push    rsi
0x180007824  push    rdi
0x180007825  push    r12
0x180007827  push    r13
0x180007829  push    r14
0x18000782b  push    r15
0x18000782d  sub     rsp, 38h
0x180007831  mov     rdi, rcx
0x180007834  mov     r12, rdx
0x180007837  add     rcx, 30h ; '0'; lpCriticalSection
0x18000783b  call    cs:__imp_EnterCriticalSection
0x180007841  mov     r13d, [rdi+98h]
0x180007848  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000784d  cmp     al, 8
0x18000784f  jb      short loc_180007878
0x180007851  mov     rcx, cs:WPP_GLOBAL_Control
0x180007858  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000785f  mov     edx, 31h ; '1'
0x180007864  mov     [rsp+78h+var_58], r12
0x180007869  mov     r9, rdi
0x18000786c  mov     rcx, [rcx+0D8h]
0x180007873  call    WPP_SF_qq
0x180007878  cmp     dword ptr [rdi+5Ch], 1
0x18000787c  jnz     loc_1800079F2
0x180007882  xor     esi, esi
0x180007884  xor     r14b, r14b
0x180007887  xor     ebp, ebp
0x180007889  cmp     ebp, r13d
0x18000788c  jnb     loc_1800079A4
0x180007892  mov     rax, [rdi+90h]
0x180007899  mov     rdx, r12
0x18000789c  mov     rcx, [rax+rbp*8]
0x1800078a0  mov     rax, [rcx]
0x1800078a3  mov     rax, [rax+40h]
0x1800078a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ac  test    al, al
0x1800078ae  jnz     short loc_1800078B4
0x1800078b0  inc     ebp
0x1800078b2  jmp     short loc_180007889
0x1800078b4  lfence
0x1800078b7  mov     rax, [rdi+90h]
0x1800078be  mov     rdx, r12
0x1800078c1  mov     rcx, [rax+rbp*8]
0x1800078c5  mov     rax, [rcx]
0x1800078c8  mov     rax, [rax+58h]
0x1800078cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d1  mov     rcx, [rdi+90h]
0x1800078d8  mov     esi, eax
0x1800078da  mov     rcx, [rcx+rbp*8]
0x1800078de  mov     rdx, [rcx]
0x1800078e1  mov     rax, [rdx+30h]
0x1800078e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ea  test    eax, eax
0x1800078ec  jnz     short loc_180007966
0x1800078ee  lfence
0x1800078f1  mov     rcx, [rdi+90h]
0x1800078f8  mov     rcx, [rcx+rbp*8]
0x1800078fc  mov     rax, [rcx]
0x1800078ff  mov     rax, [rax+98h]
0x180007906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790b  mov     edx, [rdi+98h]
0x180007911  cmp     edx, ebp
0x180007913  jbe     short loc_180007966
0x180007915  lfence
0x180007918  cmp     edx, 1
0x18000791b  jb      short loc_180007966
0x18000791d  lea     eax, [rdx-1]
0x180007920  cmp     ebp, eax
0x180007922  ja      short loc_180007966
0x180007924  mov     r9, [rdi+90h]
0x18000792b  sub     edx, ebp
0x18000792d  lea     rcx, [r9+rbp*8]; void *
0x180007931  mov     r14, [rcx]
0x180007934  sub     edx, 1
0x180007937  jz      short loc_18000794C
0x180007939  mov     r8d, edx
0x18000793c  lea     eax, [rbp+1]
0x18000793f  shl     r8, 3; Size
0x180007943  lea     rdx, [r9+rax*8]; Src
0x180007947  call    memmove_0
0x18000794c  dec     dword ptr [rdi+98h]
0x180007952  test    r14, r14
0x180007955  jz      short loc_180007966
0x180007957  mov     rax, [r14]
0x18000795a  mov     rcx, r14
0x18000795d  mov     rax, [rax+10h]
0x180007961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007966  mov     r14b, 1
0x180007969  test    esi, esi
0x18000796b  jns     short loc_1800079A4
0x18000796d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180007972  cmp     al, r14b
0x180007975  jb      short loc_18000799A
0x180007977  mov     rcx, cs:WPP_GLOBAL_Control
0x18000797e  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007985  mov     edx, 33h ; '3'
0x18000798a  mov     dword ptr [rsp+78h+var_58], esi
0x18000798e  mov     r9, rdi
0x180007991  mov     rcx, [rcx+10h]
0x180007995  call    WPP_SF_qD
0x18000799a  cmp     esi, 0C00D36D5h
0x1800079a0  jz      short loc_1800079E2
0x1800079a2  jmp     short loc_180007A23
0x1800079a4  mov     rcx, rdi; this
0x1800079a7  call    ?InternalStartIdleTimer@FSMonitorService@@IEAAJXZ; FSMonitorService::InternalStartIdleTimer(void)
0x1800079ac  test    r14b, r14b
0x1800079af  jnz     short loc_1800079E2
0x1800079b1  mov     esi, 0C00D36D5h
0x1800079b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800079bb  cmp     al, 8
0x1800079bd  jb      short loc_1800079E2
0x1800079bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079c6  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800079cd  mov     edx, 34h ; '4'
0x1800079d2  mov     dword ptr [rsp+78h+var_58], esi
0x1800079d6  mov     r9, rdi
0x1800079d9  mov     rcx, [rcx+10h]
0x1800079dd  call    WPP_SF_qD
0x1800079e2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800079e7  cmp     al, 8
0x1800079e9  jb      short loc_180007A52
0x1800079eb  mov     edx, 36h ; '6'
0x1800079f0  jmp     short loc_180007A31
0x1800079f2  mov     esi, 0C00D3E85h
0x1800079f7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800079fc  cmp     al, 1
0x1800079fe  jb      short loc_180007A23
0x180007a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a07  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007a0e  mov     edx, 32h ; '2'
0x180007a13  mov     dword ptr [rsp+78h+var_58], esi
0x180007a17  mov     r9, rdi
0x180007a1a  mov     rcx, [rcx+10h]
0x180007a1e  call    WPP_SF_qD
0x180007a23  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180007a28  cmp     al, 1
0x180007a2a  jb      short loc_180007A52
0x180007a2c  mov     edx, 35h ; '5'
0x180007a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a38  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007a3f  mov     r9, rdi
0x180007a42  mov     dword ptr [rsp+78h+var_58], esi
0x180007a46  mov     rcx, [rcx+0D8h]
0x180007a4d  call    WPP_SF_qD
0x180007a52  lea     rcx, [rdi+30h]; lpCriticalSection
0x180007a56  call    cs:__imp_LeaveCriticalSection
0x180007a5c  mov     eax, esi
0x180007a5e  add     rsp, 38h
0x180007a62  pop     r15
0x180007a64  pop     r14
0x180007a66  pop     r13
0x180007a68  pop     r12
0x180007a6a  pop     rdi
0x180007a6b  pop     rsi
0x180007a6c  pop     rbp
0x180007a6d  pop     rbx
0x180007a6e  retn
```
