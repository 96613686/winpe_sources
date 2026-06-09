# CConnectedUserStore::FinalConstruct(void)

- ea: `0x18000412c`
- end: `0x1800042ce`
- name: `?FinalConstruct@CConnectedUserStore@@QEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(CConnectedUserStore *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004300`
- `0x180010d24`

## callees

- `0x180003560`
- `0x18000412c`
- `0x18000b890`
- `0x18000c2a0`
- `0x1800144b4`
- `0x1800191ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000424c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000424c`
- `ntdll!RtlInitializeCriticalSection` at `0x1800041ca`
- `ntdll!RtlInitializeCriticalSection` at `0x1800041ca`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::FinalConstruct(CConnectedUserStore *this, __int64 a2, __int64 a3)
{
  HRESULT Instance; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  CIdentityProfileHandler *v8; // rcx
  __int64 v9; // rdx
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  HRESULT v12; // [rsp+70h] [rbp+28h] BYREF

  v12 = 0;
  v11[1] = "CConnectedUserStore::FinalConstruct";
  v11[0] = &v12;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CConnectedUserStore::FinalConstruct");
  }
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 128));
  Instance = CConnectedUserStore::InitializeDomainInfo(this);
  v12 = Instance;
  v7 = Instance;
  if ( Instance >= 0 )
  {
    Instance = CConnectedUserStore::InitializeSamHandles(this);
    v12 = Instance;
    v7 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(
                   &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
                   0,
                   0x17u,
                   &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
                   (LPVOID *)this + 23);
      v12 = Instance;
      v7 = Instance;
      if ( Instance >= 0 )
      {
LABEL_17:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_18;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v9 = 12;
        goto LABEL_16;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v9 = 11;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 10;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, (unsigned int)Instance);
      v7 = v12;
      goto LABEL_17;
    }
  }
LABEL_18:
  if ( v7 < 0 && v8 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v8 + 2), 13, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, (unsigned int)v7);
    v7 = v12;
  }
  CLogBlock::~CLogBlock((CLogBlock *)v11, v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000412c  push    rbp
0x18000412e  push    rbx
0x18000412f  push    rdi
0x180004130  push    r14
0x180004132  mov     rbp, rsp
0x180004135  sub     rsp, 48h
0x180004139  lea     r9, aCconnecteduser_19; "CConnectedUserStore::FinalConstruct"
0x180004140  mov     [rbp+arg_0], 0
0x180004147  lea     rax, [rbp+arg_0]
0x18000414b  mov     [rbp+var_10], r9
0x18000414f  mov     [rbp+var_18], rax
0x180004153  mov     rdi, rcx
0x180004156  mov     rcx, cs:WPP_GLOBAL_Control
0x18000415d  lea     r14, WPP_GLOBAL_Control
0x180004164  cmp     rcx, r14
0x180004167  jz      short loc_180004180
0x180004169  test    dword ptr [rcx+1Ch], 400h
0x180004170  jz      short loc_180004180
0x180004172  mov     rcx, [rcx+10h]
0x180004176  mov     edx, 0Ah
0x18000417b  call    WPP_SF_s
0x180004180  xorps   xmm0, xmm0
0x180004183  mov     qword ptr [rdi+58h], 0
0x18000418b  mov     qword ptr [rdi+60h], 0
0x180004193  lea     rcx, [rdi+80h]; CriticalSection
0x18000419a  mov     qword ptr [rdi+68h], 0
0x1800041a2  mov     qword ptr [rdi+70h], 0
0x1800041aa  mov     dword ptr [rdi+78h], 0
0x1800041b1  mov     qword ptr [rdi+0A8h], 0
0x1800041bc  mov     dword ptr [rdi+0B0h], 0
0x1800041c6  movups  xmmword ptr [rdi+48h], xmm0
0x1800041ca  call    cs:__imp_RtlInitializeCriticalSection
0x1800041d0  mov     rcx, rdi; this
0x1800041d3  call    ?InitializeDomainInfo@CConnectedUserStore@@AEAAJXZ; CConnectedUserStore::InitializeDomainInfo(void)
0x1800041d8  mov     [rbp+arg_0], eax
0x1800041db  mov     ebx, eax
0x1800041dd  test    eax, eax
0x1800041df  jns     short loc_180004202
0x1800041e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041e8  cmp     rcx, r14
0x1800041eb  jz      loc_18000428F
0x1800041f1  test    byte ptr [rcx+1Ch], 4
0x1800041f5  jz      loc_18000428F
0x1800041fb  mov     edx, 0Ah
0x180004200  jmp     short loc_180004272
0x180004202  mov     rcx, rdi; this
0x180004205  call    ?InitializeSamHandles@CConnectedUserStore@@AEAAJXZ; CConnectedUserStore::InitializeSamHandles(void)
0x18000420a  mov     [rbp+arg_0], eax
0x18000420d  mov     ebx, eax
0x18000420f  test    eax, eax
0x180004211  jns     short loc_18000422C
0x180004213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000421a  cmp     rcx, r14
0x18000421d  jz      short loc_18000428F
0x18000421f  test    byte ptr [rcx+1Ch], 4
0x180004223  jz      short loc_18000428F
0x180004225  mov     edx, 0Bh
0x18000422a  jmp     short loc_180004272
0x18000422c  xor     edx, edx; pUnkOuter
0x18000422e  lea     rax, [rdi+0B8h]
0x180004235  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18000423c  mov     [rsp+48h+ppv], rax; ppv
0x180004241  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x180004248  lea     r8d, [rdx+17h]; dwClsContext
0x18000424c  call    cs:__imp_CoCreateInstance
0x180004252  mov     [rbp+arg_0], eax
0x180004255  mov     ebx, eax
0x180004257  test    eax, eax
0x180004259  jns     short loc_180004288
0x18000425b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004262  cmp     rcx, r14
0x180004265  jz      short loc_18000428F
0x180004267  test    byte ptr [rcx+1Ch], 4
0x18000426b  jz      short loc_18000428F
0x18000426d  mov     edx, 0Ch
0x180004272  mov     rcx, [rcx+10h]
0x180004276  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x18000427d  mov     r9d, eax
0x180004280  call    WPP_SF_d
0x180004285  mov     ebx, [rbp+arg_0]
0x180004288  mov     rcx, cs:WPP_GLOBAL_Control
0x18000428f  test    ebx, ebx
0x180004291  jns     short loc_1800042B9
0x180004293  cmp     rcx, r14
0x180004296  jz      short loc_1800042B9
0x180004298  test    byte ptr [rcx+1Ch], 4
0x18000429c  jz      short loc_1800042B9
0x18000429e  mov     rcx, [rcx+10h]
0x1800042a2  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800042a9  mov     edx, 0Dh
0x1800042ae  mov     r9d, ebx
0x1800042b1  call    WPP_SF_d
0x1800042b6  mov     ebx, [rbp+arg_0]
0x1800042b9  lea     rcx, [rbp+var_18]; this
0x1800042bd  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800042c2  mov     eax, ebx
0x1800042c4  add     rsp, 48h
0x1800042c8  pop     r14
0x1800042ca  pop     rdi
0x1800042cb  pop     rbx
0x1800042cc  pop     rbp
0x1800042cd  retn
```
