# CAudioDeviceManager::FindAudioDevice(IMMDevice *,void * *)

- ea: `0x18000634c`
- end: `0x18000651e`
- name: `?FindAudioDevice@CAudioDeviceManager@@AEAAPEAVCAudioDevice@@PEAUIMMDevice@@PEAPEAX@Z`
- size: `466`
- prototype: `struct CAudioDevice *__fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004720`

## callees

- `0x1800035d0`
- `0x18000634c`
- `0x18002624c`
- `0x180029024`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800063e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800063e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006414`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006399`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006425`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006425`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CAudioDevice *__fastcall CAudioDeviceManager::FindAudioDevice(
        CAudioDeviceManager *this,
        struct IMMDevice *a2,
        void **a3)
{
  LPVOID v4; // r15
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  _QWORD *v6; // rcx
  _QWORD *i; // rbx
  _QWORD *v8; // r14
  int v9; // eax
  const wchar_t *v11; // r9
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  if ( ((int (__fastcall *)(struct IMMDevice *, LPVOID *))a2->lpVtbl->GetId)(a2, &pv) < 0 )
  {
    i = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
  }
  else
  {
    v4 = pv;
    v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids, v4);
      v6 = WPP_GLOBAL_Control;
    }
    for ( i = (_QWORD *)*((_QWORD *)this + 11); i; i = v8 )
    {
      v8 = (_QWORD *)*i;
      i = (_QWORD *)i[2];
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x80000) != 0 && *((_BYTE *)v6 + 25) >= 5u )
        WPP_SF_S(v6[2], 64, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids, i[1]);
      v9 = _o__wcsicmp(v4, i[1]);
      v6 = WPP_GLOBAL_Control;
      if ( !v9 )
        break;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x80000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    {
      v11 = L"Found";
      if ( !i )
        v11 = L"Did not find";
      WPP_SF_SS(v6[2], 65, (unsigned int)WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids, (_DWORD)v11, (__int64)v4);
    }
    if ( v5 )
      LeaveCriticalSection(v5);
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (struct CAudioDevice *)i;
}

```

## disassembly

```asm
0x18000634c  mov     r11, rsp
0x18000634f  mov     [r11+8], rbx
0x180006353  mov     [r11+10h], rbp
0x180006357  mov     [r11+18h], r8
0x18000635b  push    rsi
0x18000635c  push    r14
0x18000635e  push    r15
0x180006360  sub     rsp, 30h
0x180006364  mov     r8, rdx
0x180006367  mov     rbx, rcx
0x18000636a  mov     qword ptr [r11+18h], 0
0x180006372  mov     rax, [rdx]
0x180006375  lea     rdx, [r11+18h]
0x180006379  mov     rcx, r8
0x18000637c  mov     rax, [rax+28h]
0x180006380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006385  test    eax, eax
0x180006387  js      loc_180006494
0x18000638d  mov     r15, [rsp+48h+pv]
0x180006392  lea     rbp, [rbx+8]
0x180006396  mov     rcx, rbp; lpCriticalSection
0x180006399  call    cs:__imp_EnterCriticalSection
0x18000639f  lea     rsi, WPP_GLOBAL_Control
0x1800063a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063ad  cmp     rcx, rsi
0x1800063b0  jz      short loc_1800063BF
0x1800063b2  test    dword ptr [rcx+1Ch], 80000h
0x1800063b9  jnz     loc_180006466
0x1800063bf  mov     rbx, [rbx+58h]
0x1800063c3  test    rbx, rbx
0x1800063c6  jz      short loc_1800063FA
0x1800063c8  mov     r14, [rbx]
0x1800063cb  mov     rbx, [rbx+10h]
0x1800063cf  cmp     rcx, rsi
0x1800063d2  jz      short loc_1800063DD
0x1800063d4  test    dword ptr [rcx+1Ch], 80000h
0x1800063db  jnz     short loc_180006442
0x1800063dd  mov     rdx, [rbx+8]
0x1800063e1  mov     rcx, r15
0x1800063e4  call    cs:__imp__o__wcsicmp
0x1800063ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f1  test    eax, eax
0x1800063f3  jz      short loc_1800063FA
0x1800063f5  mov     rbx, r14
0x1800063f8  jmp     short loc_1800063C3
0x1800063fa  cmp     rcx, rsi
0x1800063fd  jz      short loc_18000640C
0x1800063ff  test    dword ptr [rcx+1Ch], 80000h
0x180006406  jnz     loc_1800064DF
0x18000640c  test    rbp, rbp
0x18000640f  jz      short loc_18000641B
0x180006411  mov     rcx, rbp; lpCriticalSection
0x180006414  call    cs:__imp_LeaveCriticalSection
0x18000641a  nop
0x18000641b  mov     rcx, [rsp+48h+pv]; pv
0x180006420  test    rcx, rcx
0x180006423  jz      short loc_18000642B
0x180006425  call    cs:__imp_CoTaskMemFree
0x18000642b  mov     rax, rbx
0x18000642e  mov     rbx, [rsp+48h+arg_0]
0x180006433  mov     rbp, [rsp+48h+arg_8]
0x180006438  add     rsp, 30h
0x18000643c  pop     r15
0x18000643e  pop     r14
0x180006440  pop     rsi
0x180006441  retn
0x180006442  cmp     byte ptr [rcx+19h], 5
0x180006446  jb      short loc_1800063DD
0x180006448  mov     edx, 40h ; '@'
0x18000644d  mov     r9, [rbx+8]
0x180006451  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x180006458  mov     rcx, [rcx+10h]
0x18000645c  call    WPP_SF_S
0x180006461  jmp     loc_1800063DD
0x180006466  cmp     byte ptr [rcx+19h], 5
0x18000646a  jb      loc_1800063BF
0x180006470  mov     edx, 3Fh ; '?'
0x180006475  mov     r9, r15
0x180006478  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000647f  mov     rcx, [rcx+10h]
0x180006483  call    WPP_SF_S
0x180006488  mov     rcx, cs:WPP_GLOBAL_Control
0x18000648f  jmp     loc_1800063BF
0x180006494  xor     ebx, ebx
0x180006496  lea     rsi, WPP_GLOBAL_Control
0x18000649d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064a4  cmp     rcx, rsi
0x1800064a7  jz      loc_18000641B
0x1800064ad  test    dword ptr [rcx+1Ch], 80000h
0x1800064b4  jz      loc_18000641B
0x1800064ba  cmp     byte ptr [rcx+19h], 2
0x1800064be  jb      loc_18000641B
0x1800064c4  lea     edx, [rbx+3Eh]
0x1800064c7  mov     r9d, eax
0x1800064ca  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x1800064d1  mov     rcx, [rcx+10h]
0x1800064d5  call    WPP_SF_d
0x1800064da  jmp     loc_18000641B
0x1800064df  cmp     byte ptr [rcx+19h], 4
0x1800064e3  jb      loc_18000640C
0x1800064e9  lea     rax, aDidNotFind; "Did not find"
0x1800064f0  lea     r9, aFound; "Found"
0x1800064f7  test    rbx, rbx
0x1800064fa  cmovz   r9, rax
0x1800064fe  mov     edx, 41h ; 'A'
0x180006503  mov     [rsp+48h+var_28], r15
0x180006508  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18000650f  mov     rcx, [rcx+10h]
0x180006513  call    WPP_SF_SS
0x180006518  jmp     loc_18000640C
```
