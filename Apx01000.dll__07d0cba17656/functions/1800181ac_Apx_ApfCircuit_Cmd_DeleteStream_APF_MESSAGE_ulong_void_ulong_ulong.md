# Apx::ApfCircuit::Cmd_DeleteStream(APF_MESSAGE *,ulong,void *,ulong,ulong *)

- ea: `0x1800181ac`
- end: `0x18001845d`
- name: `?Cmd_DeleteStream@ApfCircuit@Apx@@AEAAJPEAUAPF_MESSAGE@@KPEAXKPEAK@Z`
- size: `689`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct APF_MESSAGE *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017a08`

## callees

- `0x18000a12c`
- `0x18000d210`
- `0x18000d2f0`
- `0x180011f50`
- `0x1800179b0`
- `0x1800181ac`
- `0x18001a1cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018225`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018225`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuit::Cmd_DeleteStream(
        unsigned __int64 this,
        struct APF_MESSAGE *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 v9; // rbp
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rbx
  Apx::ApfCircuit *i; // rax
  Apx::ApfStream *v13; // rcx
  Apx::ApfStream **v14; // rdx
  __int64 v15; // rsi
  Apx::ApfVerify *v16; // rbx
  unsigned int v17; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  }
  *a6 = 0;
  if ( a2 && a3 >= 0x38 && *((_QWORD *)a2 + 6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 88));
    v9 = *((_QWORD *)a2 + 6);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v11 = 0;
    for ( i = *(Apx::ApfCircuit **)(this + 600); i != (Apx::ApfCircuit *)(this + 600); i = *(Apx::ApfCircuit **)i )
    {
      if ( *((_QWORD *)i - 20) == v9 )
      {
        v11 = (unsigned __int64)i - 248;
        break;
      }
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
      WPP_SF_(v10[2], 25, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
    if ( v11 )
    {
      v13 = *(Apx::ApfStream **)(v11 + 248);
      if ( *((_QWORD *)v13 + 1) != v11 + 248
        || (v14 = *(Apx::ApfStream ***)(v11 + 256), *v14 != (Apx::ApfStream *)(v11 + 248)) )
      {
        __fastfail(3u);
      }
      *v14 = v13;
      *((_QWORD *)v13 + 1) = v14;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(this + 88));
    if ( v11 )
    {
      v15 = *(_QWORD *)(v11 + 32);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qqqqi(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids,
          ~*(_QWORD *)(this + 24),
          ~this,
          ~v11,
          ~v15 & -(__int64)(v15 != 0),
          *((_QWORD *)a2 + 6));
      }
      if ( v15 )
      {
        Apx::ApfStream::RemoveIpcLink((Apx::ApfStream *)v11);
        imp_ApxObjectDelete(0, (Apx::ApfVerify *)~v15);
      }
      v16 = (Apx::ApfVerify *)~v11;
      imp_ApxObjectDereferenceActual(0, v16);
      if ( *(_QWORD *)(this + 144) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qqq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids,
            ~*(_QWORD *)(this + 24),
            ~this,
            v16);
        }
        (*(void (__fastcall **)(unsigned __int64, Apx::ApfVerify *))(this + 144))(~this, v16);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(this + 24) + 40LL))(*(_QWORD *)(this + 24));
    }
    v17 = 0;
  }
  else
  {
    v17 = -1073741811;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_1714ac20daf832ebae449f1eca86767e_Traceguids);
  }
  return v17;
}

```

## disassembly

```asm
0x1800181ac  push    rbx
0x1800181ae  push    rbp
0x1800181af  push    rsi
0x1800181b0  push    rdi
0x1800181b1  push    r12
0x1800181b3  push    r14
0x1800181b5  sub     rsp, 48h
0x1800181b9  mov     ebx, r8d
0x1800181bc  mov     r14, rdx
0x1800181bf  mov     rdi, rcx
0x1800181c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181c9  lea     r12, WPP_GLOBAL_Control
0x1800181d0  cmp     rcx, r12
0x1800181d3  jz      short loc_1800181F6
0x1800181d5  test    byte ptr [rcx+1Ch], 1
0x1800181d9  jz      short loc_1800181F6
0x1800181db  cmp     byte ptr [rcx+19h], 5
0x1800181df  jb      short loc_1800181F6
0x1800181e1  mov     rcx, [rcx+10h]
0x1800181e5  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x1800181ec  mov     edx, 26h ; '&'
0x1800181f1  call    WPP_SF_
0x1800181f6  mov     rax, [rsp+78h+arg_28]
0x1800181fe  mov     dword ptr [rax], 0
0x180018204  test    r14, r14
0x180018207  jz      loc_18001841C
0x18001820d  cmp     ebx, 38h ; '8'
0x180018210  jb      loc_18001841C
0x180018216  cmp     qword ptr [r14+30h], 0
0x18001821b  jz      loc_18001841C
0x180018221  lea     rcx, [rdi+58h]; lpCriticalSection
0x180018225  call    cs:__imp_EnterCriticalSection
0x18001822b  mov     rbp, [r14+30h]
0x18001822f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018236  cmp     rcx, r12
0x180018239  jz      short loc_180018263
0x18001823b  test    byte ptr [rcx+1Ch], 1
0x18001823f  jz      short loc_180018263
0x180018241  cmp     byte ptr [rcx+19h], 5
0x180018245  jb      short loc_180018263
0x180018247  mov     rcx, [rcx+10h]
0x18001824b  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x180018252  mov     edx, 18h
0x180018257  call    WPP_SF_
0x18001825c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018263  lea     rdx, [rdi+258h]
0x18001826a  xor     ebx, ebx
0x18001826c  mov     rax, [rdx]
0x18001826f  jmp     short loc_180018281
0x180018271  lea     r8, [rax-0F8h]
0x180018278  cmp     [r8+58h], rbp
0x18001827c  jz      short loc_180018288
0x18001827e  mov     rax, [rax]
0x180018281  cmp     rax, rdx
0x180018284  jnz     short loc_180018271
0x180018286  jmp     short loc_18001828B
0x180018288  mov     rbx, r8
0x18001828b  cmp     rcx, r12
0x18001828e  jz      short loc_1800182B1
0x180018290  test    byte ptr [rcx+1Ch], 1
0x180018294  jz      short loc_1800182B1
0x180018296  cmp     byte ptr [rcx+19h], 5
0x18001829a  jb      short loc_1800182B1
0x18001829c  mov     rcx, [rcx+10h]
0x1800182a0  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x1800182a7  mov     edx, 19h
0x1800182ac  call    WPP_SF_
0x1800182b1  test    rbx, rbx
0x1800182b4  jz      short loc_1800182DE
0x1800182b6  lea     rax, [rbx+0F8h]
0x1800182bd  mov     rcx, [rax]
0x1800182c0  cmp     [rcx+8], rax
0x1800182c4  jnz     loc_180018415
0x1800182ca  mov     rdx, [rax+8]
0x1800182ce  cmp     [rdx], rax
0x1800182d1  jnz     loc_180018415
0x1800182d7  mov     [rdx], rcx
0x1800182da  mov     [rcx+8], rdx
0x1800182de  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800182e2  call    cs:__imp_LeaveCriticalSection
0x1800182e8  test    rbx, rbx
0x1800182eb  jz      loc_180018411
0x1800182f1  mov     rsi, [rbx+20h]
0x1800182f5  mov     rbp, cs:WPP_GLOBAL_Control
0x1800182fc  cmp     rbp, r12
0x1800182ff  jz      short loc_18001835F
0x180018301  test    byte ptr [rbp+1Ch], 80h
0x180018305  jz      short loc_18001835F
0x180018307  cmp     byte ptr [rbp+19h], 4
0x18001830b  jb      short loc_18001835F
0x18001830d  mov     r9, [rdi+18h]
0x180018311  mov     rax, rsi
0x180018314  neg     rax
0x180018317  mov     rcx, rsi
0x18001831a  mov     rax, [r14+30h]
0x18001831e  not     rcx
0x180018321  mov     [rsp+78h+var_40], rax
0x180018326  sbb     r11, r11
0x180018329  and     r11, rcx
0x18001832c  mov     r10, rbx
0x18001832f  mov     rcx, [rbp+10h]
0x180018333  not     r10
0x180018336  mov     [rsp+78h+var_48], r11
0x18001833b  mov     r8, rdi
0x18001833e  not     r8
0x180018341  mov     [rsp+78h+var_50], r10
0x180018346  mov     [rsp+78h+var_58], r8
0x18001834b  not     r9
0x18001834e  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018355  mov     edx, 27h ; '''
0x18001835a  call    WPP_SF_qqqqi
0x18001835f  test    rsi, rsi
0x180018362  jz      short loc_180018379
0x180018364  mov     rcx, rbx; this
0x180018367  call    ?RemoveIpcLink@ApfStream@Apx@@QEAAXXZ; Apx::ApfStream::RemoveIpcLink(void)
0x18001836c  not     rsi
0x18001836f  xor     ecx, ecx; this
0x180018371  mov     rdx, rsi; Apx::ApfVerify *
0x180018374  call    imp_ApxObjectDelete
0x180018379  lea     rax, aOnecoreuapDriv_2; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180018380  not     rbx
0x180018383  mov     rdx, rbx; Apx::ApfVerify *
0x180018386  mov     [rsp+78h+var_58], rax
0x18001838b  mov     r9d, 367h
0x180018391  mov     r8d, 44787041h
0x180018397  xor     ecx, ecx; this
0x180018399  call    imp_ApxObjectDereferenceActual
0x18001839e  cmp     qword ptr [rdi+90h], 0
0x1800183a6  jz      short loc_180018401
0x1800183a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183af  cmp     rcx, r12
0x1800183b2  jz      short loc_1800183EC
0x1800183b4  test    byte ptr [rcx+1Ch], 80h
0x1800183b8  jz      short loc_1800183EC
0x1800183ba  cmp     byte ptr [rcx+19h], 4
0x1800183be  jb      short loc_1800183EC
0x1800183c0  mov     r9, [rdi+18h]
0x1800183c4  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x1800183cb  mov     rcx, [rcx+10h]
0x1800183cf  mov     rax, rdi
0x1800183d2  not     rax
0x1800183d5  mov     [rsp+78h+var_50], rbx
0x1800183da  not     r9
0x1800183dd  mov     [rsp+78h+var_58], rax
0x1800183e2  mov     edx, 28h ; '('
0x1800183e7  call    WPP_SF_qqq
0x1800183ec  mov     rax, [rdi+90h]
0x1800183f3  mov     rcx, rdi
0x1800183f6  not     rcx
0x1800183f9  mov     rdx, rbx
0x1800183fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018401  mov     rcx, [rdi+18h]
0x180018405  mov     rax, [rcx]
0x180018408  mov     rax, [rax+28h]
0x18001840c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018411  xor     ebx, ebx
0x180018413  jmp     short loc_180018421
0x180018415  mov     ecx, 3
0x18001841a  int     29h; Win8: RtlFailFast(ecx)
0x18001841c  mov     ebx, 0C000000Dh
0x180018421  mov     rcx, cs:WPP_GLOBAL_Control
0x180018428  cmp     rcx, r12
0x18001842b  jz      short loc_18001844E
0x18001842d  test    byte ptr [rcx+1Ch], 1
0x180018431  jz      short loc_18001844E
0x180018433  cmp     byte ptr [rcx+19h], 5
0x180018437  jb      short loc_18001844E
0x180018439  mov     rcx, [rcx+10h]
0x18001843d  lea     r8, WPP_1714ac20daf832ebae449f1eca86767e_Traceguids
0x180018444  mov     edx, 29h ; ')'
0x180018449  call    WPP_SF_
0x18001844e  mov     eax, ebx
0x180018450  add     rsp, 48h
0x180018454  pop     r14
0x180018456  pop     r12
0x180018458  pop     rdi
0x180018459  pop     rsi
0x18001845a  pop     rbp
0x18001845b  pop     rbx
0x18001845c  retn
```
