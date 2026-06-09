# ShieldProvider::GetPersistedKey(ushort const *,ushort const *,ushort * *)

- ea: `0x140007248`
- end: `0x14000737d`
- name: `?GetPersistedKey@ShieldProvider@@YAJPEBG0PEAPEAG@Z`
- size: `309`
- prototype: `__int64 __fastcall(ShieldProvider *this, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140007384`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140007248`
- `0x14001010c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x14000728a`
- `ntdll!RtlGetPersistedStateLocation` at `0x140007327`
- `ntdll!RtlGetPersistedStateLocation` at `0x14000728a`
- `ntdll!RtlGetPersistedStateLocation` at `0x140007327`
- `ntdll!RtlNtStatusToDosError` at `0x14000732f`
- `ntdll!RtlNtStatusToDosError` at `0x14000732f`

## string_xrefs

- `0x140007272`: `Windows Security Health`
- `0x14000730f`: `Windows Security Health`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetPersistedKey(
        ShieldProvider *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  void *v4; // rbx
  NTSTATUS PersistedStateLocation; // eax
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rdx
  unsigned int v10; // edi
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  unsigned int v16; // [rsp+60h] [rbp+8h] BYREF
  int v17; // [rsp+64h] [rbp+Ch]
  void *v18; // [rsp+78h] [rbp+20h] BYREF

  v17 = HIDWORD(this);
  v4 = 0;
  v18 = 0;
  v16 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(L"Windows Security Health", 0, a2, 0, 0, 0, &v16);
  if ( PersistedStateLocation == -2147483643 )
  {
    v9 = v16;
    if ( v16 < 2uLL )
    {
      v10 = -2147024809;
LABEL_5:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 26;
LABEL_8:
        WPP_SF_d(v12[2], v13, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, v10);
        goto LABEL_9;
      }
      goto LABEL_9;
    }
    v11 = CommonUtil::MpNewAlloc((CommonUtil *)&v18, (void **)v16, v8);
    v4 = v18;
    v10 = v11;
    if ( v11 < 0 )
      goto LABEL_5;
    PersistedStateLocation = RtlGetPersistedStateLocation(L"Windows Security Health", 0, a2, 0, v18, v16, &v16);
  }
  v14 = RtlNtStatusToDosError(PersistedStateLocation);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0x80070000;
  if ( (v10 & 0x80000000) == 0 )
  {
    *(_QWORD *)a3 = v4;
    return v10;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 27;
    goto LABEL_8;
  }
LABEL_9:
  if ( v4 )
    operator delete(v4, v9);
  return v10;
}

```

## disassembly

```asm
0x140007248  mov     rax, rsp
0x14000724b  mov     [rax+10h], rbx
0x14000724f  mov     [rax+8], rcx
0x140007253  push    rbp
0x140007254  push    rsi
0x140007255  push    rdi
0x140007256  sub     rsp, 40h
0x14000725a  xor     ebx, ebx
0x14000725c  mov     rsi, r8
0x14000725f  mov     [rax+20h], rbx
0x140007263  mov     rbp, rdx
0x140007266  mov     [rax+8], ebx
0x140007269  lea     rax, [rax+8]
0x14000726d  mov     [rsp+58h+var_28], rax
0x140007272  lea     rcx, aWindowsSecurit; "Windows Security Health"
0x140007279  mov     r8, rdx
0x14000727c  mov     [rsp+58h+var_30], ebx
0x140007280  xor     r9d, r9d
0x140007283  mov     [rsp+58h+var_38], rbx
0x140007288  xor     edx, edx
0x14000728a  call    cs:__imp_RtlGetPersistedStateLocation
0x140007290  cmp     eax, 80000005h
0x140007295  jnz     loc_14000732D
0x14000729b  mov     edx, dword ptr [rsp+58h+arg_0]; void **
0x14000729f  cmp     rdx, 2
0x1400072a3  jnb     short loc_1400072AC
0x1400072a5  mov     edi, 80070057h
0x1400072aa  jmp     short loc_1400072C1
0x1400072ac  lea     rcx, [rsp+58h+arg_18]; this
0x1400072b1  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x1400072b6  mov     rbx, [rsp+58h+arg_18]
0x1400072bb  mov     edi, eax
0x1400072bd  test    eax, eax
0x1400072bf  jns     short loc_140007301
0x1400072c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072c8  lea     rax, WPP_GLOBAL_Control
0x1400072cf  cmp     rcx, rax
0x1400072d2  jz      short loc_1400072F2
0x1400072d4  test    byte ptr [rcx+1Ch], 1
0x1400072d8  jz      short loc_1400072F2
0x1400072da  mov     edx, 1Ah
0x1400072df  mov     rcx, [rcx+10h]
0x1400072e3  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1400072ea  mov     r9d, edi
0x1400072ed  call    WPP_SF_d
0x1400072f2  test    rbx, rbx
0x1400072f5  jz      short loc_14000736E
0x1400072f7  mov     rcx, rbx; void *
0x1400072fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400072ff  jmp     short loc_14000736E
0x140007301  mov     eax, dword ptr [rsp+58h+arg_0]
0x140007305  lea     rdx, [rsp+58h+arg_0]
0x14000730a  mov     [rsp+58h+var_28], rdx
0x14000730f  lea     rcx, aWindowsSecurit; "Windows Security Health"
0x140007316  mov     [rsp+58h+var_30], eax
0x14000731a  xor     edx, edx
0x14000731c  xor     r9d, r9d
0x14000731f  mov     [rsp+58h+var_38], rbx
0x140007324  mov     r8, rbp
0x140007327  call    cs:__imp_RtlGetPersistedStateLocation
0x14000732d  mov     ecx, eax; Status
0x14000732f  call    cs:__imp_RtlNtStatusToDosError
0x140007335  mov     edi, eax
0x140007337  test    eax, eax
0x140007339  jle     short loc_140007344
0x14000733b  movzx   edi, ax
0x14000733e  or      edi, 80070000h
0x140007344  test    edi, edi
0x140007346  jns     short loc_14000736B
0x140007348  mov     rcx, cs:WPP_GLOBAL_Control
0x14000734f  lea     rax, WPP_GLOBAL_Control
0x140007356  cmp     rcx, rax
0x140007359  jz      short loc_1400072F2
0x14000735b  test    byte ptr [rcx+1Ch], 1
0x14000735f  jz      short loc_1400072F2
0x140007361  mov     edx, 1Bh
0x140007366  jmp     loc_1400072DF
0x14000736b  mov     [rsi], rbx
0x14000736e  mov     rbx, [rsp+58h+arg_8]
0x140007373  mov     eax, edi
0x140007375  add     rsp, 40h
0x140007379  pop     rdi
0x14000737a  pop     rsi
0x14000737b  pop     rbp
0x14000737c  retn
```
