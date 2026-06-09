# CPort::PerformPMKIDRequest(ulong,DOT11_NWF_BSSID_CANDIDATE *)

- ea: `0x140089258`
- end: `0x14008956f`
- name: `?PerformPMKIDRequest@CPort@@QEAAKKPEAUDOT11_NWF_BSSID_CANDIDATE@@@Z`
- size: `791`
- prototype: `unsigned int __fastcall(CPort *__hidden this, unsigned int, struct DOT11_NWF_BSSID_CANDIDATE *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140084a9c`
- `0x1400a22d4`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x140018270`
- `0x14001eed0`
- `0x14002aaec`
- `0x14002bd34`
- `0x14002ed50`
- `0x14003895c`
- `0x140082f60`
- `0x140089258`
- `0x14008e168`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CPort::PerformPMKIDRequest(CPort *this, unsigned int a2, struct DOT11_NWF_BSSID_CANDIDATE *a3)
{
  unsigned int v4; // esi
  int v6; // edx
  unsigned int v7; // edi
  unsigned int v8; // r15d
  struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *v9; // rax
  int v10; // edx
  int v11; // r8d
  struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *v12; // r14
  int v13; // r12d
  int PropertyULongOrDefault; // edi
  unsigned __int64 CurrentTime; // rax
  int v16; // edx
  int v17; // r8d
  unsigned int v18; // edi
  char v19; // al
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  int v25; // [rsp+20h] [rbp-88h]
  unsigned int v26[2]; // [rsp+28h] [rbp-80h]
  unsigned __int64 v27; // [rsp+B0h] [rbp+8h]

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      323,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v6 = *((_DWORD *)this + 97);
  if ( !v6 || !v4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        (unsigned int)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        324,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (char)this,
        *((_WORD *)this + 74),
        *((_DWORD *)this + 97),
        v4);
    }
    return 0;
  }
  v7 = 40;
  if ( v4 <= 0x28 )
    v7 = v4;
  v8 = 16 * v7 + 12;
  v9 = (struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)operator new(v8);
  v12 = v9;
  if ( !v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        325,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (char)this,
        *((_WORD *)this + 74));
    }
    return 0;
  }
  memset(v9, 0, 16 * v7 + 12);
  v12->Header = (NDIS_OBJECT_HEADER)786816;
  v13 = CPort::BuildNwfPmkidParamList(this, v4, a3, v7, v12);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault((CPort *)((char *)this + 480), 0x2Du, 0);
  CPropertyCache::GetPropertyULongOrDefault((CPort *)((char *)this + 480), 0x2Eu, 0);
  CurrentTime = CSystem::get_CurrentTime();
  v27 = CurrentTime;
  if ( CurrentTime < *((_QWORD *)this + 70) + 600000000LL )
  {
    v18 = PropertyULongOrDefault + 1;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        v17,
        326,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        (char)this,
        *((_WORD *)this + 74),
        PropertyULongOrDefault);
    }
    v18 = 1;
    CPropertyCache::SetPropertyULong((CPort *)((char *)this + 480), 0x2Eu, 0);
    CurrentTime = v27;
  }
  *((_QWORD *)this + 70) = CurrentTime;
  CPropertyCache::SetPropertyULong((CPort *)((char *)this + 480), 0x2Du, v18);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = CPropertyCache::GetPropertyULongOrDefault((CPort *)((char *)this + 480), 0x2Eu, 0);
    WPP_RECORDER_SF_qDDddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      v21,
      v22,
      v25,
      (char)this,
      *((_WORD *)this + 74),
      v13,
      v4,
      v18,
      v19);
  }
  CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), v13, 0, v12, v8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v26[0] = 0;
    LOBYTE(v23) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      1,
      328,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      *(_QWORD *)v26);
  }
  operator delete(v12);
  return v18;
}

```

## disassembly

```asm
0x140089258  push    rbx
0x14008925a  push    rbp
0x14008925b  push    rsi
0x14008925c  push    rdi
0x14008925d  push    r12
0x14008925f  push    r13
0x140089261  push    r14
0x140089263  push    r15
0x140089265  sub     rsp, 68h
0x140089269  mov     r12, r8
0x14008926c  mov     esi, edx
0x14008926e  mov     rbx, rcx
0x140089271  lea     rax, WPP_RECORDER_INITIALIZED
0x140089278  xor     r13d, r13d
0x14008927b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140089282  lea     r8, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140089289  jz      short loc_1400892C9
0x14008928b  mov     rcx, cs:WPP_GLOBAL_Control
0x140089292  cmp     byte ptr [rcx+29h], 5
0x140089296  jnb     short loc_14008929F
0x140089298  cmp     [rcx+48h], r13w
0x14008929d  jz      short loc_1400892C9
0x14008929f  mov     rcx, [rcx+40h]
0x1400892a3  mov     r9d, 143h
0x1400892a9  mov     [rsp+0A8h+var_88], r8
0x1400892ae  mov     dl, 5
0x1400892b0  mov     r8d, 1
0x1400892b6  call    WPP_RECORDER_SF_
0x1400892bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400892c2  lea     r8, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400892c9  mov     edx, [rbx+184h]
0x1400892cf  test    edx, edx
0x1400892d1  jz      loc_140089510
0x1400892d7  test    esi, esi
0x1400892d9  jz      loc_140089510
0x1400892df  mov     edi, 28h ; '('
0x1400892e4  cmp     esi, edi
0x1400892e6  cmovbe  edi, esi
0x1400892e9  mov     r15d, edi
0x1400892ec  shl     r15d, 4
0x1400892f0  add     r15d, 0Ch
0x1400892f4  mov     ecx, r15d; unsigned __int64
0x1400892f7  mov     ebp, r15d
0x1400892fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400892ff  mov     r14, rax
0x140089302  test    rax, rax
0x140089305  jnz     short loc_140089354
0x140089307  lea     rax, WPP_RECORDER_INITIALIZED
0x14008930e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140089315  jz      loc_14008955B
0x14008931b  movzx   eax, word ptr [rbx+94h]
0x140089322  mov     r9d, 145h
0x140089328  mov     rcx, cs:WPP_GLOBAL_Control
0x14008932f  mov     dl, 2
0x140089331  mov     [rsp+0A8h+var_78], eax
0x140089335  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008933c  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140089341  mov     [rsp+0A8h+var_88], rax
0x140089346  mov     rcx, [rcx+40h]
0x14008934a  call    WPP_RECORDER_SF_qD
0x14008934f  jmp     loc_14008955B
0x140089354  mov     r8, rbp; Size
0x140089357  xor     edx, edx; Val
0x140089359  mov     rcx, r14; void *
0x14008935c  call    memset
0x140089361  mov     r9d, edi; unsigned int
0x140089364  mov     dword ptr [r14], 0C0180h
0x14008936b  mov     r8, r12; struct DOT11_NWF_BSSID_CANDIDATE *
0x14008936e  mov     [rsp+0A8h+var_88], r14; struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *
0x140089373  mov     edx, esi; unsigned int
0x140089375  mov     rcx, rbx; this
0x140089378  call    ?BuildNwfPmkidParamList@CPort@@QEAAHKPEAUDOT11_NWF_BSSID_CANDIDATE@@KPEAUDOT11_PMKID_CANDIDATE_LIST_PARAMETERS@@@Z; CPort::BuildNwfPmkidParamList(ulong,DOT11_NWF_BSSID_CANDIDATE *,ulong,DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)
0x14008937d  xor     r8d, r8d; unsigned int
0x140089380  lea     rbp, [rbx+1E0h]
0x140089387  mov     rcx, rbp; this
0x14008938a  mov     r12d, eax
0x14008938d  lea     edx, [r8+2Dh]; unsigned int
0x140089391  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140089396  xor     r8d, r8d; unsigned int
0x140089399  mov     rcx, rbp; this
0x14008939c  mov     edi, eax
0x14008939e  lea     edx, [r8+2Eh]; unsigned int
0x1400893a2  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400893a7  mov     r13d, eax
0x1400893aa  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400893af  mov     rcx, [rbx+230h]
0x1400893b6  add     rcx, 23C34600h
0x1400893bd  mov     [rsp+0A8h+arg_0], rax
0x1400893c5  cmp     rax, rcx
0x1400893c8  jb      short loc_140089434
0x1400893ca  lea     rax, WPP_RECORDER_INITIALIZED
0x1400893d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400893d8  jz      short loc_140089417
0x1400893da  movzx   ecx, word ptr [rbx+94h]
0x1400893e1  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400893e8  mov     [rsp+0A8h+var_68], r13d
0x1400893ed  mov     r9d, 146h
0x1400893f3  mov     [rsp+0A8h+var_70], edi
0x1400893f7  mov     dl, 4
0x1400893f9  mov     [rsp+0A8h+var_78], ecx
0x1400893fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140089404  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140089409  mov     [rsp+0A8h+var_88], rax
0x14008940e  mov     rcx, [rcx+40h]
0x140089412  call    WPP_RECORDER_SF_qDdd
0x140089417  mov     edi, 1
0x14008941c  xor     r8d, r8d; unsigned int
0x14008941f  mov     rcx, rbp; this
0x140089422  lea     edx, [rdi+2Dh]; unsigned int
0x140089425  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14008942a  mov     rax, [rsp+0A8h+arg_0]
0x140089432  jmp     short loc_140089436
0x140089434  inc     edi
0x140089436  mov     r8d, edi; unsigned int
0x140089439  mov     [rbx+230h], rax
0x140089440  mov     edx, 2Dh ; '-'; unsigned int
0x140089445  mov     rcx, rbp; this
0x140089448  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x14008944d  lea     r13, WPP_RECORDER_INITIALIZED
0x140089454  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008945b  jz      short loc_14008949D
0x14008945d  xor     r8d, r8d; unsigned int
0x140089460  mov     rcx, rbp; this
0x140089463  lea     edx, [r8+2Eh]; unsigned int
0x140089467  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x14008946c  movzx   ecx, word ptr [rbx+94h]
0x140089473  mov     [rsp+0A8h+var_58], eax
0x140089477  mov     [rsp+0A8h+var_60], edi
0x14008947b  mov     [rsp+0A8h+var_68], esi
0x14008947f  mov     [rsp+0A8h+var_70], r12d
0x140089484  mov     [rsp+0A8h+var_78], ecx
0x140089488  mov     rcx, cs:WPP_GLOBAL_Control
0x14008948f  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140089494  mov     rcx, [rcx+40h]
0x140089498  call    WPP_RECORDER_SF_qDDddd
0x14008949d  mov     edx, [rbx+90h]; unsigned int
0x1400894a3  xor     r9d, r9d; void *
0x1400894a6  mov     rcx, [rbx+88h]; this
0x1400894ad  mov     r8d, r12d; int
0x1400894b0  mov     [rsp+0A8h+var_80], r15d; unsigned int
0x1400894b5  mov     [rsp+0A8h+var_88], r14; void *
0x1400894ba  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x1400894bf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400894c6  jz      short loc_140089504
0x1400894c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400894cf  xor     eax, eax
0x1400894d1  cmp     byte ptr [rcx+29h], 5
0x1400894d5  jnb     short loc_1400894DD
0x1400894d7  cmp     [rcx+48h], ax
0x1400894db  jz      short loc_140089504
0x1400894dd  mov     rcx, [rcx+40h]
0x1400894e1  mov     r9d, 148h
0x1400894e7  mov     [rsp+0A8h+var_80], eax
0x1400894eb  mov     r8d, 1
0x1400894f1  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400894f8  mov     dl, 5
0x1400894fa  mov     [rsp+0A8h+var_88], rax
0x1400894ff  call    WPP_RECORDER_SF_d
0x140089504  mov     rcx, r14; void *
0x140089507  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008950c  mov     eax, edi
0x14008950e  jmp     short loc_14008955D
0x140089510  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140089517  jz      short loc_14008955B
0x140089519  mov     rcx, cs:WPP_GLOBAL_Control
0x140089520  cmp     byte ptr [rcx+29h], 5
0x140089524  jnb     short loc_14008952D
0x140089526  cmp     [rcx+48h], r13w
0x14008952b  jz      short loc_14008955B
0x14008952d  movzx   eax, word ptr [rbx+94h]
0x140089534  mov     r9d, 144h
0x14008953a  mov     rcx, [rcx+40h]
0x14008953e  mov     [rsp+0A8h+var_68], esi
0x140089542  mov     [rsp+0A8h+var_70], edx
0x140089546  mov     dl, 5
0x140089548  mov     [rsp+0A8h+var_78], eax
0x14008954c  mov     qword ptr [rsp+0A8h+var_80], rbx
0x140089551  mov     [rsp+0A8h+var_88], r8
0x140089556  call    WPP_RECORDER_SF_qDdd
0x14008955b  xor     eax, eax
0x14008955d  add     rsp, 68h
0x140089561  pop     r15
0x140089563  pop     r14
0x140089565  pop     r13
0x140089567  pop     r12
0x140089569  pop     rdi
0x14008956a  pop     rsi
0x14008956b  pop     rbp
0x14008956c  pop     rbx
0x14008956d  retn
```
