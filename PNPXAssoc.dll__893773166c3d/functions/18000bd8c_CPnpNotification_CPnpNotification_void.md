# CPnpNotification::~CPnpNotification(void)

- ea: `0x18000bd8c`
- end: `0x18000bf67`
- name: `??1CPnpNotification@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(CPnpNotification *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bf70`

## callees

- `0x18000bce4`
- `0x18000bd8c`
- `0x18000c33c`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000beb0`
- `KERNEL32!LeaveCriticalSection` at `0x18000beb0`
- `KERNEL32!EnterCriticalSection` at `0x18000be72`
- `KERNEL32!EnterCriticalSection` at `0x18000be72`
- `KERNEL32!DeleteCriticalSection` at `0x18000bf17`
- `KERNEL32!DeleteCriticalSection` at `0x18000bf57`
- `KERNEL32!DeleteCriticalSection` at `0x18000bf17`
- `KERNEL32!DeleteCriticalSection` at `0x18000bf57`

## pseudocode

```c
void __fastcall CPnpNotification::~CPnpNotification(CPnpNotification *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rdx
  struct _NOTIFICATION_ITEM **v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // rcx
  struct _NOTIFICATION_ITEM *v8; // rax
  struct _NOTIFICATION_ITEM *v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  struct _NOTIFICATION_ITEM *v12; // rdx
  _QWORD *v13; // rcx
  struct _NOTIFICATION_ITEM *v14[2]; // [rsp+30h] [rbp-18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 15);
  if ( v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 16LL))(*((_QWORD *)this + 15));
    *((_QWORD *)this + 15) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 16LL))(*((_QWORD *)this + 14));
    *((_QWORD *)this + 14) = 0;
    v2 = WPP_GLOBAL_Control;
  }
  g_pPnpNotification = 0;
  *(_OWORD *)v14 = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_sq(v2[2], 56, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  v14[1] = (struct _NOTIFICATION_ITEM *)v14;
  v14[0] = (struct _NOTIFICATION_ITEM *)v14;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v5 = (struct _NOTIFICATION_ITEM **)((char *)this + 128);
  while ( 1 )
  {
    v9 = *v5;
    if ( *v5 == (struct _NOTIFICATION_ITEM *)v5 )
      break;
    v6 = (_QWORD *)*((_QWORD *)v9 + 1);
    v7 = *(_QWORD *)v9;
    *v6 = *(_QWORD *)v9;
    *(_QWORD *)(v7 + 8) = v6;
    v8 = v14[1];
    *(_QWORD *)v9 = v14;
    *((_QWORD *)v9 + 1) = v8;
    *(_QWORD *)v8 = v9;
    v14[1] = v9;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  while ( 1 )
  {
    v12 = v14[0];
    if ( (struct _NOTIFICATION_ITEM **)v14[0] == v14 )
      break;
    v10 = *(_QWORD *)v14[0];
    v11 = (_QWORD *)*((_QWORD *)v14[0] + 1);
    *v11 = *(_QWORD *)v14[0];
    *(_QWORD *)(v10 + 8) = v11;
    CPnpNotification::FreeNotificationItem(this, v12);
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 16) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_sq(v13[2], 13, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000bd8c  push    rbp
0x18000bd8e  push    rbx
0x18000bd8f  push    rdi
0x18000bd90  push    r15
0x18000bd92  mov     rbp, rsp
0x18000bd95  sub     rsp, 48h
0x18000bd99  mov     rbx, rcx
0x18000bd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bda3  lea     r15, WPP_GLOBAL_Control
0x18000bdaa  cmp     rcx, r15
0x18000bdad  jz      short loc_18000BDD6
0x18000bdaf  cmp     byte ptr [rcx+19h], 4
0x18000bdb3  jb      short loc_18000BDD6
0x18000bdb5  mov     rcx, [rcx+10h]
0x18000bdb9  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000bdc0  mov     edx, 0Ch
0x18000bdc5  mov     [rsp+48h+var_28], rbx
0x18000bdca  call    WPP_SF_sq
0x18000bdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdd6  mov     rdx, [rbx+78h]
0x18000bdda  test    rdx, rdx
0x18000bddd  jz      short loc_18000BDFD
0x18000bddf  mov     rax, [rdx]
0x18000bde2  mov     rcx, rdx
0x18000bde5  mov     rax, [rax+10h]
0x18000bde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdee  mov     qword ptr [rbx+78h], 0
0x18000bdf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdfd  mov     rdx, [rbx+70h]
0x18000be01  test    rdx, rdx
0x18000be04  jz      short loc_18000BE24
0x18000be06  mov     rax, [rdx]
0x18000be09  mov     rcx, rdx
0x18000be0c  mov     rax, [rax+10h]
0x18000be10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be15  mov     qword ptr [rbx+70h], 0
0x18000be1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be24  xorps   xmm0, xmm0
0x18000be27  mov     cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA, 0; CPnpNotification * g_pPnpNotification
0x18000be32  movups  xmmword ptr [rbp+var_18], xmm0
0x18000be36  cmp     rcx, r15
0x18000be39  jz      short loc_18000BE5B
0x18000be3b  cmp     byte ptr [rcx+19h], 4
0x18000be3f  jb      short loc_18000BE5B
0x18000be41  mov     rcx, [rcx+10h]
0x18000be45  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000be4c  mov     edx, 38h ; '8'
0x18000be51  mov     [rsp+48h+var_28], rbx
0x18000be56  call    WPP_SF_sq
0x18000be5b  lea     rax, [rbp+var_18]
0x18000be5f  mov     [rbp+var_18+8], rax
0x18000be63  lea     rdi, [rbx+48h]
0x18000be67  lea     rax, [rbp+var_18]
0x18000be6b  mov     rcx, rdi; lpCriticalSection
0x18000be6e  mov     [rbp+var_18], rax
0x18000be72  call    cs:__imp_EnterCriticalSection
0x18000be78  lea     r8, [rbx+80h]
0x18000be7f  jmp     short loc_18000BEA5
0x18000be81  mov     rax, [rdx+8]
0x18000be85  mov     rcx, [rdx]
0x18000be88  mov     [rax], rcx
0x18000be8b  mov     [rcx+8], rax
0x18000be8f  lea     rcx, [rbp+var_18]
0x18000be93  mov     rax, [rbp+var_18+8]
0x18000be97  mov     [rdx], rcx
0x18000be9a  mov     [rdx+8], rax
0x18000be9e  mov     [rax], rdx
0x18000bea1  mov     [rbp+var_18+8], rdx
0x18000bea5  mov     rdx, [r8]
0x18000bea8  cmp     rdx, r8
0x18000beab  jnz     short loc_18000BE81
0x18000bead  mov     rcx, rdi; lpCriticalSection
0x18000beb0  call    cs:__imp_LeaveCriticalSection
0x18000beb6  jmp     short loc_18000BECE
0x18000beb8  mov     rcx, [rdx]
0x18000bebb  mov     rax, [rdx+8]
0x18000bebf  mov     [rax], rcx
0x18000bec2  mov     [rcx+8], rax
0x18000bec6  mov     rcx, rbx; this
0x18000bec9  call    ?FreeNotificationItem@CPnpNotification@@IEAAXPEAU_NOTIFICATION_ITEM@@@Z; CPnpNotification::FreeNotificationItem(_NOTIFICATION_ITEM *)
0x18000bece  mov     rdx, [rbp+var_18]; struct _NOTIFICATION_ITEM *
0x18000bed2  lea     rax, [rbp+var_18]
0x18000bed6  cmp     rdx, rax
0x18000bed9  jnz     short loc_18000BEB8
0x18000bedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bee2  cmp     rcx, r15
0x18000bee5  jz      short loc_18000BF0E
0x18000bee7  cmp     byte ptr [rcx+19h], 4
0x18000beeb  jb      short loc_18000BF0E
0x18000beed  mov     rcx, [rcx+10h]
0x18000bef1  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000bef8  mov     edx, 39h ; '9'
0x18000befd  mov     [rsp+48h+var_28], rbx
0x18000bf02  call    WPP_SF_sq
0x18000bf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf0e  cmp     dword ptr [rbx+40h], 0
0x18000bf12  jz      short loc_18000BF24
0x18000bf14  mov     rcx, rdi; lpCriticalSection
0x18000bf17  call    cs:__imp_DeleteCriticalSection
0x18000bf1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf24  cmp     rcx, r15
0x18000bf27  jz      short loc_18000BF49
0x18000bf29  cmp     byte ptr [rcx+19h], 4
0x18000bf2d  jb      short loc_18000BF49
0x18000bf2f  mov     rcx, [rcx+10h]
0x18000bf33  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000bf3a  mov     edx, 0Dh
0x18000bf3f  mov     [rsp+48h+var_28], rbx
0x18000bf44  call    WPP_SF_sq
0x18000bf49  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000bf4d  cmp     byte ptr [rcx+28h], 0
0x18000bf51  jz      short loc_18000BF5D
0x18000bf53  mov     byte ptr [rcx+28h], 0
0x18000bf57  call    cs:__imp_DeleteCriticalSection
0x18000bf5d  add     rsp, 48h
0x18000bf61  pop     r15
0x18000bf63  pop     rdi
0x18000bf64  pop     rbx
0x18000bf65  pop     rbp
0x18000bf66  retn
```
