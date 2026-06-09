# UbpmpRunSerializedActionCallback(void *,uchar,void *)

- ea: `0x18000f880`
- end: `0x18000fbe1`
- name: `?UbpmpRunSerializedActionCallback@@YAXPEAXE0@Z`
- size: `865`
- prototype: `void __fastcall(void *, unsigned __int8, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800048b0`
- `0x180008720`
- `0x180008920`
- `0x18000dda4`
- `0x18000e0a8`
- `0x18000f880`
- `0x18000fbf0`
- `0x1800101a0`
- `0x1800119a0`
- `0x180012570`
- `0x1800265d0`
- `0x180032f78`
- `0x180037598`
- `0x180038458`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000faf3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000faf3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f916`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000f916`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f930`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000f930`

## pseudocode

```c
void __fastcall UbpmpRunSerializedActionCallback(char *a1, char a2, void *a3)
{
  unsigned __int16 v3; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  DWORD v10; // ebx
  int v11; // esi
  signed __int32 v12; // ecx
  signed __int32 v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  void *v23; // rcx
  int v24; // ecx
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // [rsp+20h] [rbp-E0h]
  _BYTE v28[4]; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+78h] [rbp-88h]
  DWORD LengthSid; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  char v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  char v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  _BYTE v37[144]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  if ( *((_WORD *)a1 + 10) != 1 )
    v3 = *((_WORD *)a1 + 10);
  memset_0(v28, 0, 0x48u);
  if ( (a2 & 4) == 0 )
  {
    memset_0(v37, 0, 0x88u);
    UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v37);
    v9 = UbpmpOpenTriggerConsumer((UUID *)(a1 + 24), 0);
    v10 = UbpmpLockTrackerId;
    v11 = v9;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v10, 0);
    }
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *((unsigned __int16 *)a1 + 10));
    }
    else
    {
      v12 = *((_DWORD *)a1 + 10);
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)0x2C, v12, v12);
      v7 = *((unsigned int *)a1 + 10);
      if ( v12 == v13 )
      {
        if ( !(unsigned int)UbpmConsumerIncPendingActions(0) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_SddiL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v7,
              *(_QWORD *)(MEMORY[0x18] + 8LL),
              *((_WORD *)a1 + 10),
              *((_DWORD *)a1 + 10),
              *((_QWORD *)a1 + 9),
              *((_DWORD *)a1 + 25));
          if ( *((_WORD *)a1 + 10) == 1 )
          {
            if ( !(unsigned __int8)UbpmCheckAndMarkOneActiveTask((UUID *)(a1 + 4)) )
              UbpmRunConsumerQueuedActions(0, 0, 0);
          }
          else
          {
            v23 = (void *)*((_QWORD *)a1 + 8);
            v30 = *((_DWORD *)a1 + 14);
            if ( v23 )
              LengthSid = GetLengthSid(v23);
            else
              LengthSid = 0;
            v24 = *((_DWORD *)a1 + 25);
            v32 = *((_QWORD *)a1 + 8);
            v33 = a1[104];
            v34 = *((_QWORD *)a1 + 14);
            v35 = a1[120];
            v36 = *((_QWORD *)a1 + 16);
            v29 = v24;
            v25 = *(_QWORD *)(MEMORY[0x18] + 40LL);
            if ( *(_DWORD *)(v25 + 40LL * v3 - 24) == 1 )
            {
              v26 = *(_QWORD *)(*(_QWORD *)(v25 + 40LL * v3 - 16) + 32LL);
              if ( v26 )
              {
                if ( *(_DWORD *)(v26 + 32) == 2 )
                  v29 = v24 | 6;
              }
            }
            UbpmRunConsumerActions(
              0,
              v27,
              *((_QWORD *)a1 + 9),
              *((_DWORD *)a1 + 20),
              *((_DWORD *)a1 + 21),
              *((_QWORD *)a1 + 11),
              (struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)v28,
              0);
          }
          UbpmConsumerDecPendingActions(0);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Sddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
          *(_QWORD *)(MEMORY[0x18] + 8LL),
          211,
          MEMORY[0x2C],
          v7);
      }
    }
  }
  if ( (a1[96] & 1) != 0 )
    UbpmpRemoveQueuedSerialActions((UUID *)(a1 + 4), 0, 0, 0, v3);
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 14), v6, v7, v8);
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 16), v14, v15, v16);
  UBPM_MIDL_user_free(*((_QWORD *)a1 + 11), v17, v18, v19);
  UBPM_MIDL_user_free(a1, v20, v21, v22);
}

```

## disassembly

```asm
0x18000f880  push    rbp
0x18000f882  push    rbx
0x18000f883  push    rsi
0x18000f884  push    rdi
0x18000f885  push    r12
0x18000f887  push    r14
0x18000f889  lea     rbp, [rsp-68h]
0x18000f88e  sub     rsp, 168h
0x18000f895  mov     rax, cs:__security_cookie
0x18000f89c  xor     rax, rsp
0x18000f89f  mov     [rbp+90h+var_40], rax
0x18000f8a3  xor     r14d, r14d
0x18000f8a6  mov     [rsp+190h+var_130], 0
0x18000f8af  mov     bl, dl
0x18000f8b1  mov     rdi, rcx
0x18000f8b4  lea     r12d, [r14+1]
0x18000f8b8  cmp     [rcx+14h], r12w
0x18000f8bd  lea     r8d, [r12+47h]; Size
0x18000f8c2  cmovnz  r14w, [rcx+14h]
0x18000f8c8  xor     edx, edx; Val
0x18000f8ca  lea     rcx, [rsp+190h+var_120]; void *
0x18000f8cf  call    memset_0
0x18000f8d4  test    bl, 4
0x18000f8d7  jnz     loc_18000F9C7
0x18000f8dd  xor     edx, edx; Val
0x18000f8df  lea     rcx, [rbp+90h+var_D0]; void *
0x18000f8e3  mov     r8d, 88h; Size
0x18000f8e9  call    memset_0
0x18000f8ee  lea     rcx, [rbp+90h+var_D0]; lpTlsValue
0x18000f8f2  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18000f8f7  lea     rcx, [rdi+18h]; Uuid2
0x18000f8fb  xor     edx, edx; String2
0x18000f8fd  lea     r8, [rsp+190h+var_130]
0x18000f902  call    UbpmpOpenTriggerConsumer
0x18000f907  mov     ebx, cs:UbpmpLockTrackerId
0x18000f90d  mov     esi, eax
0x18000f90f  cmp     ebx, 0FFFFFFFFh
0x18000f912  jz      short loc_18000F93C
0x18000f914  mov     ecx, ebx; dwTlsIndex
0x18000f916  call    cs:__imp_TlsGetValue
0x18000f91d  nop     dword ptr [rax+rax+00h]
0x18000f922  cmp     qword ptr [rax], 0
0x18000f926  jnz     loc_18000FA50
0x18000f92c  xor     edx, edx; lpTlsValue
0x18000f92e  mov     ecx, ebx; dwTlsIndex
0x18000f930  call    cs:__imp_TlsSetValue
0x18000f937  nop     dword ptr [rax+rax+00h]
0x18000f93c  mov     rbx, [rsp+190h+var_130]
0x18000f941  test    esi, esi
0x18000f943  jnz     loc_18000FA14
0x18000f949  mov     ecx, [rdi+28h]
0x18000f94c  mov     eax, ecx
0x18000f94e  lock cmpxchg [rbx+2Ch], ecx
0x18000f953  mov     r8d, [rdi+28h]
0x18000f957  jnz     loc_18000FA57
0x18000f95d  mov     rcx, rbx
0x18000f960  call    UbpmConsumerIncPendingActions
0x18000f965  test    eax, eax
0x18000f967  jnz     short loc_18000F9BA
0x18000f969  mov     rdx, cs:WPP_GLOBAL_Control
0x18000f970  lea     rax, WPP_GLOBAL_Control
0x18000f977  cmp     rdx, rax
0x18000f97a  jz      short loc_18000F989
0x18000f97c  test    dword ptr [rdx+1Ch], 200h
0x18000f983  jnz     loc_18000FAAE
0x18000f989  movzx   r8d, word ptr [rdi+14h]
0x18000f98e  cmp     r8w, r12w
0x18000f992  jnz     loc_18000FAE3
0x18000f998  lea     rcx, [rdi+4]; Uuid2
0x18000f99c  call    UbpmCheckAndMarkOneActiveTask
0x18000f9a1  test    al, al
0x18000f9a3  jnz     short loc_18000F9B2
0x18000f9a5  xor     r8d, r8d
0x18000f9a8  xor     edx, edx
0x18000f9aa  mov     rcx, rbx
0x18000f9ad  call    UbpmRunConsumerQueuedActions
0x18000f9b2  mov     rcx, rbx
0x18000f9b5  call    UbpmConsumerDecPendingActions
0x18000f9ba  test    rbx, rbx
0x18000f9bd  jz      short loc_18000F9C7
0x18000f9bf  mov     rcx, rbx
0x18000f9c2  call    UbpmCloseTriggerConsumer
0x18000f9c7  test    [rdi+60h], r12b
0x18000f9cb  jnz     loc_18000FBC5
0x18000f9d1  mov     rcx, [rdi+70h]
0x18000f9d5  call    UBPM_MIDL_user_free
0x18000f9da  mov     rcx, [rdi+80h]
0x18000f9e1  call    UBPM_MIDL_user_free
0x18000f9e6  mov     rcx, [rdi+58h]
0x18000f9ea  call    UBPM_MIDL_user_free
0x18000f9ef  mov     rcx, rdi
0x18000f9f2  call    UBPM_MIDL_user_free
0x18000f9f7  mov     rcx, [rbp+90h+var_40]
0x18000f9fb  xor     rcx, rsp; StackCookie
0x18000f9fe  call    __security_check_cookie
0x18000fa03  add     rsp, 168h
0x18000fa0a  pop     r14
0x18000fa0c  pop     r12
0x18000fa0e  pop     rdi
0x18000fa0f  pop     rsi
0x18000fa10  pop     rbx
0x18000fa11  pop     rbp
0x18000fa12  retn
0x18000fa14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa1b  lea     rax, WPP_GLOBAL_Control
0x18000fa22  cmp     rcx, rax
0x18000fa25  jz      short loc_18000F9BA
0x18000fa27  test    [rcx+1Ch], r12b
0x18000fa2b  jz      short loc_18000F9BA
0x18000fa2d  movzx   r9d, word ptr [rdi+14h]
0x18000fa32  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000fa39  mov     rcx, [rcx+10h]
0x18000fa3d  mov     edx, 52h ; 'R'
0x18000fa42  mov     dword ptr [rsp+190h+var_170], esi
0x18000fa46  call    WPP_SF_dd
0x18000fa4b  jmp     loc_18000F9BA
0x18000fa50  int     2Ch; Windows NT - assertion failure
0x18000fa52  jmp     loc_18000F92C
0x18000fa57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa5e  lea     rax, WPP_GLOBAL_Control
0x18000fa65  cmp     rcx, rax
0x18000fa68  jz      loc_18000F9BA
0x18000fa6e  test    [rcx+1Ch], r12b
0x18000fa72  jz      loc_18000F9BA
0x18000fa78  mov     rax, [rbx+18h]
0x18000fa7c  mov     edx, 53h ; 'S'
0x18000fa81  mov     rcx, [rcx+10h]
0x18000fa85  mov     [rsp+190h+var_160], r8d
0x18000fa8a  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000fa91  mov     r9, [rax+8]
0x18000fa95  mov     eax, [rbx+2Ch]
0x18000fa98  mov     dword ptr [rsp+190h+var_168], eax
0x18000fa9c  mov     dword ptr [rsp+190h+var_170], 4D3h
0x18000faa4  call    WPP_SF_Sddd
0x18000faa9  jmp     loc_18000F9BA
0x18000faae  mov     eax, [rdi+64h]
0x18000fab1  movzx   ecx, word ptr [rdi+14h]
0x18000fab5  mov     r9, [rbx+18h]
0x18000fab9  mov     [rsp+190h+var_158], eax
0x18000fabd  mov     rax, [rdi+48h]
0x18000fac1  mov     qword ptr [rsp+190h+var_160], rax
0x18000fac6  mov     eax, [rdi+28h]
0x18000fac9  mov     r9, [r9+8]
0x18000facd  mov     dword ptr [rsp+190h+var_168], eax
0x18000fad1  mov     dword ptr [rsp+190h+var_170], ecx
0x18000fad5  mov     rcx, [rdx+10h]
0x18000fad9  call    WPP_SF_SddiL
0x18000fade  jmp     loc_18000F989
0x18000fae3  mov     rcx, [rdi+40h]; pSid
0x18000fae7  mov     eax, [rdi+38h]
0x18000faea  mov     [rsp+190h+var_118], eax
0x18000faee  test    rcx, rcx
0x18000faf1  jz      short loc_18000FB09
0x18000faf3  call    cs:__imp_GetLengthSid
0x18000fafa  nop     dword ptr [rax+rax+00h]
0x18000faff  movzx   r8d, word ptr [rdi+14h]
0x18000fb04  mov     [rbp+90h+var_110], eax
0x18000fb07  jmp     short loc_18000FB10
0x18000fb09  mov     [rbp+90h+var_110], 0
0x18000fb10  mov     rax, [rdi+40h]
0x18000fb14  mov     ecx, [rdi+64h]
0x18000fb17  mov     [rbp+90h+var_108], rax
0x18000fb1b  mov     al, [rdi+68h]
0x18000fb1e  mov     [rbp+90h+var_F8], al
0x18000fb21  mov     rax, [rdi+70h]
0x18000fb25  mov     [rbp+90h+var_F0], rax
0x18000fb29  mov     al, [rdi+78h]
0x18000fb2c  mov     [rbp+90h+var_E8], al
0x18000fb2f  mov     rax, [rdi+80h]
0x18000fb36  mov     [rbp+90h+var_E0], rax
0x18000fb3a  mov     [rsp+190h+var_11C], ecx
0x18000fb3e  movzx   eax, r14w
0x18000fb42  lea     rdx, [rax+rax*4]
0x18000fb46  mov     rax, [rbx+18h]
0x18000fb4a  mov     rax, [rax+28h]
0x18000fb4e  cmp     [rax+rdx*8-18h], r12d
0x18000fb53  jnz     short loc_18000FB70
0x18000fb55  mov     rax, [rax+rdx*8-10h]
0x18000fb5a  mov     rdx, [rax+20h]
0x18000fb5e  test    rdx, rdx
0x18000fb61  jz      short loc_18000FB70
0x18000fb63  cmp     dword ptr [rdx+20h], 2
0x18000fb67  jnz     short loc_18000FB70
0x18000fb69  or      ecx, 6
0x18000fb6c  mov     [rsp+190h+var_11C], ecx
0x18000fb70  mov     [rsp+190h+var_140], 0; __int64
0x18000fb79  lea     rax, [rsp+190h+var_120]
0x18000fb7e  mov     [rsp+190h+var_148], rax; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x18000fb83  lea     r9, [rdi+4]
0x18000fb87  mov     rax, [rdi+58h]
0x18000fb8b  mov     rdx, r12
0x18000fb8e  mov     [rsp+190h+var_150], rax; __int64
0x18000fb93  mov     eax, [rdi+54h]
0x18000fb96  mov     [rsp+190h+var_158], eax; unsigned int
0x18000fb9a  mov     eax, [rdi+50h]
0x18000fb9d  movzx   ecx, r8w
0x18000fba1  mov     r8, [rdi+30h]
0x18000fba5  sub     ecx, r12d
0x18000fba8  mov     [rsp+190h+var_160], eax; unsigned int
0x18000fbac  mov     rax, [rdi+48h]
0x18000fbb0  shl     rdx, cl
0x18000fbb3  mov     rcx, rbx; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000fbb6  mov     [rsp+190h+var_168], rax; unsigned __int64
0x18000fbbb  call    UbpmRunConsumerActions
0x18000fbc0  jmp     loc_18000F9B2
0x18000fbc5  lea     rcx, [rdi+4]; Uuid1
0x18000fbc9  mov     [rsp+190h+var_170], r14w; __int16
0x18000fbcf  xor     r9d, r9d
0x18000fbd2  xor     r8d, r8d; UUID *
0x18000fbd5  xor     edx, edx; UUID *
0x18000fbd7  call    UbpmpRemoveQueuedSerialActions
0x18000fbdc  jmp     loc_18000F9D1
```
