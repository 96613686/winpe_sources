# SessionFrameDecoder::ProcessInput(void *,ulong,__int64,__int64)

- ea: `0x180012818`
- end: `0x1800129dd`
- name: `?ProcessInput@SessionFrameDecoder@@QEAAJPEAXK_J1@Z`
- size: `453`
- prototype: `__int64 __fastcall(CVideoObjectDecoder **this, void *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012580`

## callees

- `0x1800111bc`
- `0x180012818`
- `0x180012a08`
- `0x18002aac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012915`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001290b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001290b`

## pseudocode

```c
__int64 __fastcall SessionFrameDecoder::ProcessInput(
        CVideoObjectDecoder **this,
        void *a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v7; // edi
  char *v8; // rbx
  CVideoObjectDecoder *v10; // rax
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-61h] BYREF
  int v13; // [rsp+24h] [rbp-5Dh] BYREF
  __int64 v14; // [rsp+28h] [rbp-59h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-51h] BYREF
  _QWORD v16[6]; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v17[6]; // [rsp+70h] [rbp-11h] BYREF
  int v18; // [rsp+F0h] [rbp+6Fh] BYREF

  v18 = a3;
  v14 = a4;
  if ( g_petwPro )
  {
    v16[5] = 8;
    v16[1] = 4;
    v16[0] = &v18;
    v16[3] = 8;
    v16[2] = &v14;
    v16[4] = &a5;
    ETWWrite(this, MP4SDECD_ProcessInput_Notification_Start, 3, v16);
    a3 = v18;
  }
  if ( a2 && this[2] )
  {
    v10 = this[3];
    *(_QWORD *)v10 = a2;
    *((_DWORD *)v10 + 2) = a3;
    *((_QWORD *)v10 + 2) = 0;
    *((_DWORD *)v10 + 3) = 0;
    v7 = CVideoObjectDecoder::ProcessInput(this[2], v14, a5);
    if ( v7 == -7 )
    {
      if ( g_petwPro )
      {
        v11 = *((unsigned int *)this[2] + 210);
        v17[0] = &v12;
        v17[2] = &v14;
        v17[4] = &a5;
        v12 = v11;
        v17[1] = 4;
        v17[3] = 8;
        v17[5] = 8;
        ETWWrite(v11, MP4SDECD_ProcessInput_Notification_Drop, 3, v17);
      }
      v7 = 0;
    }
  }
  else
  {
    v7 = -100;
  }
  v8 = (char *)g_petwPro;
  if ( g_petwPro )
  {
    UserData.Ptr = 0;
    *(_QWORD *)&UserData.Size = 0;
    v13 = *((_DWORD *)this[2] + 210);
    UserData.Ptr = (ULONGLONG)&v13;
    *(_QWORD *)&UserData.Size = 4;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_petwPro + 16));
    if ( !*(_DWORD *)v8 )
      EventWrite(*((_QWORD *)v8 + 1), &MP4SDECD_ProcessInput_Notification_Stop, 1u, &UserData);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
  }
  return v7;
}

```

## disassembly

```asm
0x180012818  mov     [rsp-8+arg_10], r8d
0x18001281d  push    rbp
0x18001281e  push    rbx
0x18001281f  push    rsi
0x180012820  push    rdi
0x180012821  push    r14
0x180012823  lea     rbp, [rsp-2Fh]
0x180012828  sub     rsp, 0B0h
0x18001282f  mov     rax, cs:__security_cookie
0x180012836  xor     rax, rsp
0x180012839  mov     [rbp+4Fh+var_30], rax
0x18001283d  xor     r14d, r14d
0x180012840  mov     [rbp+4Fh+var_A8], r9
0x180012844  cmp     cs:g_petwPro, r14
0x18001284b  mov     rbx, rdx
0x18001284e  mov     rsi, rcx
0x180012851  jz      short loc_1800128A6
0x180012853  xorps   xmm0, xmm0
0x180012856  mov     [rbp+4Fh+var_68], 8
0x18001285e  movups  [rbp+4Fh+var_88], xmm0
0x180012862  lea     rax, [rbp+4Fh+arg_10]
0x180012866  mov     qword ptr [rbp+4Fh+var_88], 4
0x18001286e  mov     [rbp+4Fh+var_90], rax
0x180012872  lea     r9, [rbp+4Fh+var_90]
0x180012876  movups  [rbp+4Fh+var_78], xmm0
0x18001287a  lea     rax, [rbp+4Fh+var_A8]
0x18001287e  mov     qword ptr [rbp+4Fh+var_78], 8
0x180012886  mov     qword ptr [rbp+4Fh+var_88+8], rax
0x18001288a  lea     r8d, [r14+3]
0x18001288e  lea     rax, [rbp+4Fh+arg_20]
0x180012892  lea     rdx, MP4SDECD_ProcessInput_Notification_Start
0x180012899  mov     qword ptr [rbp+4Fh+var_78+8], rax
0x18001289d  call    ETWWrite
0x1800128a2  mov     r8d, [rbp+4Fh+arg_10]
0x1800128a6  test    rbx, rbx
0x1800128a9  jnz     loc_180012937
0x1800128af  mov     edi, 0FFFFFF9Ch
0x1800128b4  mov     rbx, cs:g_petwPro
0x1800128bb  test    rbx, rbx
0x1800128be  jz      short loc_18001291B
0x1800128c0  xor     eax, eax
0x1800128c2  mov     [rbp+4Fh+UserData.Ptr], r14
0x1800128c6  mov     qword ptr [rbp+4Fh+UserData.Size], rax
0x1800128ca  mov     rax, [rsi+10h]
0x1800128ce  mov     ecx, [rax+348h]
0x1800128d4  lea     rax, [rbp+4Fh+var_AC]
0x1800128d8  mov     [rbp+4Fh+var_AC], ecx
0x1800128db  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800128df  mov     [rbp+4Fh+UserData.Ptr], rax
0x1800128e3  mov     qword ptr [rbp+4Fh+UserData.Size], 4
0x1800128eb  call    cs:__imp_EnterCriticalSection
0x1800128f1  cmp     [rbx], r14d
0x1800128f4  jnz     short loc_180012911
0x1800128f6  mov     rcx, [rbx+8]; RegHandle
0x1800128fa  lea     r9, [rbp+4Fh+UserData]; UserData
0x1800128fe  mov     r8d, 1; UserDataCount
0x180012904  lea     rdx, MP4SDECD_ProcessInput_Notification_Stop; EventDescriptor
0x18001290b  call    cs:__imp_EventWrite
0x180012911  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012915  call    cs:__imp_LeaveCriticalSection
0x18001291b  mov     eax, edi
0x18001291d  mov     rcx, [rbp+4Fh+var_30]
0x180012921  xor     rcx, rsp; StackCookie
0x180012924  call    __security_check_cookie
0x180012929  add     rsp, 0B0h
0x180012930  pop     r14
0x180012932  pop     rdi
0x180012933  pop     rsi
0x180012934  pop     rbx
0x180012935  pop     rbp
0x180012936  retn
0x180012937  cmp     [rsi+10h], r14
0x18001293b  jz      loc_1800128AF
0x180012941  mov     rax, [rsi+18h]
0x180012945  mov     [rax], rbx
0x180012948  mov     [rax+8], r8d
0x18001294c  mov     [rax+10h], r14
0x180012950  mov     [rax+0Ch], r14d
0x180012954  mov     r8, [rbp+4Fh+arg_20]; __int64
0x180012958  mov     rdx, [rbp+4Fh+var_A8]; __int64
0x18001295c  mov     rcx, [rsi+10h]; this
0x180012960  call    ?ProcessInput@CVideoObjectDecoder@@QEAAJ_J0@Z; CVideoObjectDecoder::ProcessInput(__int64,__int64)
0x180012965  mov     edi, eax
0x180012967  cmp     eax, 0FFFFFFF9h
0x18001296a  jnz     loc_1800128B4
0x180012970  cmp     cs:g_petwPro, r14
0x180012977  jz      short loc_1800129D5
0x180012979  mov     rax, [rsi+10h]
0x18001297d  lea     r9, [rbp+4Fh+var_60]
0x180012981  xorps   xmm0, xmm0
0x180012984  lea     r8d, [rdi+0Ah]
0x180012988  lea     rdx, MP4SDECD_ProcessInput_Notification_Drop
0x18001298f  mov     ecx, [rax+348h]
0x180012995  lea     rax, [rbp+4Fh+var_B0]
0x180012999  mov     [rbp+4Fh+var_60], rax
0x18001299d  lea     rax, [rbp+4Fh+var_A8]
0x1800129a1  movups  [rbp+4Fh+var_58], xmm0
0x1800129a5  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x1800129a9  lea     rax, [rbp+4Fh+arg_20]
0x1800129ad  movups  [rbp+4Fh+var_48], xmm0
0x1800129b1  mov     qword ptr [rbp+4Fh+var_48+8], rax
0x1800129b5  mov     [rbp+4Fh+var_B0], ecx
0x1800129b8  mov     qword ptr [rbp+4Fh+var_58], 4
0x1800129c0  mov     qword ptr [rbp+4Fh+var_48], 8
0x1800129c8  mov     [rbp+4Fh+var_38], 8
0x1800129d0  call    ETWWrite
0x1800129d5  mov     edi, r14d
0x1800129d8  jmp     loc_1800128B4
```
