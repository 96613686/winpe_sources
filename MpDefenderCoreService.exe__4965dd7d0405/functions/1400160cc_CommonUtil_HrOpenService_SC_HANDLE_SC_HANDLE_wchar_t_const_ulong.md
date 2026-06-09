# CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)

- ea: `0x1400160cc`
- end: `0x140016189`
- name: `?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z`
- size: `189`
- prototype: `int(CommonUtil *__hidden this, struct SC_HANDLE__ **, struct SC_HANDLE__ *, const wchar_t *, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140016538`
- `0x1400885c0`
- `0x140089c78`
- `0x14008af18`
- `0x1400c49c8`
- `0x1400f5998`

## callees

- `0x1400160cc`
- `0x140017738`
- `0x140085d94`
- `0x14008d178`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x1400160f0`
- `ADVAPI32!OpenServiceW` at `0x1400160f0`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrOpenService(
        CommonUtil *this,
        struct SC_HANDLE__ **a2,
        const WCHAR *a3,
        const wchar_t *a4)
{
  int v4; // esi
  char v6; // di
  SC_HANDLE v7; // rax
  unsigned int LastFailure; // eax
  unsigned int v9; // ebx

  v4 = (int)a3;
  v6 = (char)a4;
  v7 = OpenServiceW((SC_HANDLE)a2, a3, (DWORD)a4);
  if ( v7 )
  {
    *(_QWORD *)this = v7;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        v4,
        v6);
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    v9 = LastFailure;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_SLd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        v4,
        v6,
        LastFailure);
    return v9;
  }
}

```

## disassembly

```asm
0x1400160cc  mov     [rsp+arg_0], rbx
0x1400160d1  mov     [rsp+arg_8], rsi
0x1400160d6  push    rdi
0x1400160d7  sub     rsp, 30h
0x1400160db  mov     rsi, r8
0x1400160de  mov     rax, rdx
0x1400160e1  mov     rbx, rcx
0x1400160e4  mov     rdx, rsi; lpServiceName
0x1400160e7  mov     rcx, rax; hSCManager
0x1400160ea  mov     r8d, r9d; dwDesiredAccess
0x1400160ed  mov     edi, r9d
0x1400160f0  call    cs:__imp_OpenServiceW
0x1400160f6  test    rax, rax
0x1400160f9  jnz     short loc_14001613F
0x1400160fb  call    HrGetLastFailure
0x140016100  mov     ebx, eax
0x140016102  mov     rcx, cs:WPP_GLOBAL_Control
0x140016109  lea     rdx, WPP_GLOBAL_Control
0x140016110  cmp     rcx, rdx
0x140016113  jz      short loc_14001613B
0x140016115  test    byte ptr [rcx+1Ch], 1
0x140016119  jz      short loc_14001613B
0x14001611b  mov     rcx, [rcx+10h]
0x14001611f  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016126  mov     [rsp+38h+var_10], eax
0x14001612a  mov     edx, 0Bh
0x14001612f  mov     r9, rsi
0x140016132  mov     [rsp+38h+var_18], edi
0x140016136  call    WPP_SF_SLd
0x14001613b  mov     eax, ebx
0x14001613d  jmp     short loc_140016179
0x14001613f  mov     [rbx], rax
0x140016142  mov     rcx, cs:WPP_GLOBAL_Control
0x140016149  lea     rdx, WPP_GLOBAL_Control
0x140016150  cmp     rcx, rdx
0x140016153  jz      short loc_140016177
0x140016155  test    byte ptr [rcx+1Ch], 4
0x140016159  jz      short loc_140016177
0x14001615b  mov     rcx, [rcx+10h]
0x14001615f  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016166  mov     edx, 0Ch
0x14001616b  mov     [rsp+38h+var_18], edi
0x14001616f  mov     r9, rsi
0x140016172  call    WPP_SF_Sd
0x140016177  xor     eax, eax
0x140016179  mov     rbx, [rsp+38h+arg_0]
0x14001617e  mov     rsi, [rsp+38h+arg_8]
0x140016183  add     rsp, 30h
0x140016187  pop     rdi
0x140016188  retn
```
