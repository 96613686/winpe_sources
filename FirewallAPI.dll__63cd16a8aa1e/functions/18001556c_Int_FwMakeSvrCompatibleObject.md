# Int_FwMakeSvrCompatibleObject

- ea: `0x18001556c`
- end: `0x1800157e4`
- name: `Int_FwMakeSvrCompatibleObject`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001494c`

## callees

- `0x180005954`
- `0x18001556c`
- `0x1800277b0`
- `0x18005e010`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18001569c`
- `fwbase!FwHResultToWindowsError` at `0x180015744`
- `fwbase!FwHResultToWindowsError` at `0x1800157a5`
- `fwbase!FwHResultToWindowsError` at `0x18001569c`
- `fwbase!FwHResultToWindowsError` at `0x180015744`
- `fwbase!FwHResultToWindowsError` at `0x1800157a5`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001573c`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001579d`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001573c`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001579d`
- `FWPolicyIOMgr!FwFreeSets` at `0x180015780`
- `FWPolicyIOMgr!FwFreeSets` at `0x180015780`

## pseudocode

```c
__int64 __fastcall Int_FwMakeSvrCompatibleObject(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 a3,
        __int64 (__fastcall *a4)(__int64, _QWORD *),
        __int64 (__fastcall *a5)(__int64, int *),
        unsigned __int16 a6,
        int a7,
        _DWORD *a8)
{
  unsigned int v8; // ebx
  unsigned int v14; // eax
  FwPolicy2 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  int v22; // [rsp+28h] [rbp-50h] BYREF

  v8 = 0;
  v22 = 0x10000;
  v21 = 0;
  *a2 = 0;
  if ( a3 >= 0x221u )
    goto LABEL_2;
  v14 = a5(a1, &v22);
  v8 = v14;
  if ( v14 != 87 && v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v16 = 379;
    goto LABEL_9;
  }
  if ( v22 == 0x40000 )
  {
    v8 = 50;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 380;
      v17 = 50;
      goto LABEL_10;
    }
    return v8;
  }
  if ( v22 != 0x10000 )
  {
    v18 = a4(a1, a2);
    v14 = FwHResultToWindowsError(v18);
    v8 = v14;
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v16 = 381;
    }
    else
    {
      v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))a5)(*a2, 0, a3);
      v8 = v14;
      if ( !v14 )
        goto LABEL_2;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v16 = 382;
    }
LABEL_9:
    v17 = v14;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v17);
    return v8;
  }
LABEL_2:
  if ( a7 == 3 && a6 < 0x214u )
  {
    if ( *a2 )
    {
      v19 = FwCopyAuthSetToLowerVersion(522, *a2, &v21);
      v14 = FwHResultToWindowsError(v19);
      v8 = v14;
      if ( !v14 )
      {
        FwFreeSets(*a2, 0);
        *a2 = v21;
        *a8 = 1;
        return v8;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 383;
        goto LABEL_9;
      }
    }
    else
    {
      v20 = FwCopyAuthSetToLowerVersion(522, a1, &v21);
      v14 = FwHResultToWindowsError(v20);
      v8 = v14;
      if ( !v14 )
      {
        *a2 = v21;
        return v8;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 384;
        goto LABEL_9;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001556c  push    rbx
0x18001556e  push    rbp
0x18001556f  push    rsi
0x180015570  push    rdi
0x180015571  push    r12
0x180015573  push    r14
0x180015575  push    r15
0x180015577  sub     rsp, 40h
0x18001557b  mov     rax, cs:__security_cookie
0x180015582  xor     rax, rsp
0x180015585  mov     [rsp+78h+var_48], rax
0x18001558a  mov     r14, [rsp+78h+arg_20]
0x180015592  xor     ebx, ebx
0x180015594  mov     r15, [rsp+78h+arg_38]
0x18001559c  mov     eax, 221h
0x1800155a1  mov     [rsp+78h+var_50], 10000h
0x1800155a9  mov     r12, r9
0x1800155ac  mov     [rsp+78h+var_58], rbx
0x1800155b1  movzx   ebp, r8w
0x1800155b5  mov     [rdx], rbx
0x1800155b8  mov     rdi, rdx
0x1800155bb  mov     rsi, rcx
0x1800155be  cmp     r8w, ax
0x1800155c2  jb      short loc_1800155F0
0x1800155c4  cmp     [rsp+78h+arg_30], 3
0x1800155cc  jz      loc_180015719
0x1800155d2  mov     eax, ebx
0x1800155d4  mov     rcx, [rsp+78h+var_48]
0x1800155d9  xor     rcx, rsp; StackCookie
0x1800155dc  call    __security_check_cookie
0x1800155e1  add     rsp, 40h
0x1800155e5  pop     r15
0x1800155e7  pop     r14
0x1800155e9  pop     r12
0x1800155eb  pop     rdi
0x1800155ec  pop     rsi
0x1800155ed  pop     rbp
0x1800155ee  pop     rbx
0x1800155ef  retn
0x1800155f0  lea     rdx, [rsp+78h+var_50]
0x1800155f5  mov     rax, r14
0x1800155f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155fd  mov     ebx, eax
0x1800155ff  cmp     eax, 57h ; 'W'
0x180015602  jz      short loc_18001564C
0x180015604  test    eax, eax
0x180015606  jz      short loc_18001564C
0x180015608  mov     rcx, cs:WPP_GLOBAL_Control
0x18001560f  lea     rdx, WPP_GLOBAL_Control
0x180015616  cmp     rcx, rdx
0x180015619  jz      short loc_1800155D2
0x18001561b  test    byte ptr [rcx+1Ch], 1
0x18001561f  jz      short loc_1800155D2
0x180015621  mov     edx, 17Bh
0x180015626  jmp     short loc_18001562D
0x180015628  mov     edx, 180h
0x18001562d  mov     r9d, eax
0x180015630  jmp     short loc_18001563A
0x180015632  mov     edx, 17Ch
0x180015637  mov     r9d, ebx
0x18001563a  mov     rcx, [rcx+10h]
0x18001563e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180015645  call    WPP_SF_d
0x18001564a  jmp     short loc_1800155D2
0x18001564c  cmp     [rsp+78h+var_50], 40000h
0x180015654  jnz     short loc_18001567E
0x180015656  mov     ebx, 32h ; '2'
0x18001565b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015662  lea     rdx, WPP_GLOBAL_Control
0x180015669  cmp     rcx, rdx
0x18001566c  jz      loc_1800155D2
0x180015672  test    byte ptr [rcx+1Ch], 1
0x180015676  jz      loc_1800155D2
0x18001567c  jmp     short loc_180015632
0x18001567e  cmp     [rsp+78h+var_50], 10000h
0x180015686  jz      loc_1800155C4
0x18001568c  mov     rdx, rdi
0x18001568f  mov     rcx, rsi
0x180015692  mov     rax, r12
0x180015695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001569a  mov     ecx, eax
0x18001569c  call    cs:__imp_FwHResultToWindowsError
0x1800156a2  mov     ebx, eax
0x1800156a4  test    eax, eax
0x1800156a6  jz      short loc_1800156D3
0x1800156a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156af  lea     rdx, WPP_GLOBAL_Control
0x1800156b6  cmp     rcx, rdx
0x1800156b9  jz      loc_1800155D2
0x1800156bf  test    byte ptr [rcx+1Ch], 1
0x1800156c3  jz      loc_1800155D2
0x1800156c9  mov     edx, 17Dh
0x1800156ce  jmp     loc_18001562D
0x1800156d3  mov     rcx, [rdi]
0x1800156d6  movzx   r8d, bp
0x1800156da  xor     edx, edx
0x1800156dc  mov     rax, r14
0x1800156df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e4  mov     ebx, eax
0x1800156e6  test    eax, eax
0x1800156e8  jz      loc_1800155C4
0x1800156ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156f5  lea     rdx, WPP_GLOBAL_Control
0x1800156fc  cmp     rcx, rdx
0x1800156ff  jz      loc_1800155D2
0x180015705  test    byte ptr [rcx+1Ch], 1
0x180015709  jz      loc_1800155D2
0x18001570f  mov     edx, 17Eh
0x180015714  jmp     loc_18001562D
0x180015719  mov     eax, 214h
0x18001571e  cmp     [rsp+78h+arg_28], ax
0x180015726  jnb     loc_1800155D2
0x18001572c  mov     rdx, [rdi]
0x18001572f  lea     ecx, [rax-0Ah]
0x180015732  lea     r8, [rsp+78h+var_58]
0x180015737  test    rdx, rdx
0x18001573a  jz      short loc_18001579A
0x18001573c  call    cs:__imp_FwCopyAuthSetToLowerVersion
0x180015742  mov     ecx, eax
0x180015744  call    cs:__imp_FwHResultToWindowsError
0x18001574a  mov     ebx, eax
0x18001574c  test    eax, eax
0x18001574e  jz      short loc_18001577B
0x180015750  mov     rcx, cs:WPP_GLOBAL_Control
0x180015757  lea     rdx, WPP_GLOBAL_Control
0x18001575e  cmp     rcx, rdx
0x180015761  jz      loc_1800155D2
0x180015767  test    byte ptr [rcx+1Ch], 1
0x18001576b  jz      loc_1800155D2
0x180015771  mov     edx, 17Fh
0x180015776  jmp     loc_18001562D
0x18001577b  mov     rcx, [rdi]
0x18001577e  xor     edx, edx
0x180015780  call    cs:__imp_FwFreeSets
0x180015786  mov     rax, [rsp+78h+var_58]
0x18001578b  mov     [rdi], rax
0x18001578e  mov     dword ptr [r15], 1
0x180015795  jmp     loc_1800155D2
0x18001579a  mov     rdx, rsi
0x18001579d  call    cs:__imp_FwCopyAuthSetToLowerVersion
0x1800157a3  mov     ecx, eax
0x1800157a5  call    cs:__imp_FwHResultToWindowsError
0x1800157ab  mov     ebx, eax
0x1800157ad  test    eax, eax
0x1800157af  jz      short loc_1800157D7
0x1800157b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157b8  lea     rdx, WPP_GLOBAL_Control
0x1800157bf  cmp     rcx, rdx
0x1800157c2  jz      loc_1800155D2
0x1800157c8  test    byte ptr [rcx+1Ch], 1
0x1800157cc  jz      loc_1800155D2
0x1800157d2  jmp     loc_180015628
0x1800157d7  mov     rax, [rsp+78h+var_58]
0x1800157dc  mov     [rdi], rax
0x1800157df  jmp     loc_1800155D2
```
