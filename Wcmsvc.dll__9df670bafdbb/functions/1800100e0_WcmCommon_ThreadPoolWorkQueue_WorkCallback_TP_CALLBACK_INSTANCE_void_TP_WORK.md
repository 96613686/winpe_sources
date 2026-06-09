# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800100e0`
- end: `0x18001055a`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1146`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180010080`
- `0x1800100e0`
- `0x180010560`
- `0x180011218`
- `0x180031408`
- `0x18006ff48`
- `0x1800721b8`
- `0x180084f50`
- `0x180085be8`
- `0x1800f7010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001040e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001040e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001011d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001011d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010418`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010418`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800103e0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800103e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800103d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800103d7`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        char *a2,
        struct _TP_WORK *a3)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // r8
  bool v9; // zf
  std::_Ref_count_base **v10; // rsi
  std::_Ref_count_base *v11; // rcx
  void (*v12)(void); // rax
  std::_Ref_count_base **v13; // rdx
  HANDLE CurrentThread; // rax
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rcx
  std::_Ref_count_base **pExceptionObject; // [rsp+20h] [rbp-39h] BYREF
  __int128 v19; // [rsp+28h] [rbp-31h]
  std::_Ref_count_base *v20[2]; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base **v21; // [rsp+78h] [rbp+1Fh]
  char v22; // [rsp+80h] [rbp+27h]

  v21 = 0;
  v22 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(a2 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  if ( *(_DWORD *)a2 != 1 )
  {
    if ( *((_QWORD *)a2 + 33) )
    {
      pExceptionObject = v20;
      v8 = *(_QWORD *)(*((_QWORD *)a2 + 30) + 8 * (*((_QWORD *)a2 + 32) & (*((_QWORD *)a2 + 31) - 1LL)));
      pExceptionObject = v20;
      *(_QWORD *)&v19 = v8;
      *((_QWORD *)&v19 + 1) = v20;
      ____Visit_V_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___1_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__4__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___2_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__1__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
        *(char *)(v8 + 64) + 1LL,
        &pExceptionObject);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(*(_QWORD *)(*((_QWORD *)a2 + 30) + 8 * (*((_QWORD *)a2 + 32) & (*((_QWORD *)a2 + 31) - 1LL))));
      v9 = (*((_QWORD *)a2 + 33))-- == 1;
      if ( v9 )
        *((_QWORD *)a2 + 32) = 0;
      else
        ++*((_QWORD *)a2 + 32);
      goto LABEL_26;
    }
    if ( v4 )
LABEL_15:
      LeaveCriticalSection(v4);
LABEL_19:
    if ( v21 )
    {
      v13 = v20;
      LOBYTE(v13) = v21 != v20;
      (*((void (__fastcall **)(std::_Ref_count_base **, std::_Ref_count_base **))*v21 + 4))(v21, v13);
    }
    return;
  }
  if ( !*((_QWORD *)a2 + 28) )
  {
    if ( *((_QWORD *)a2 + 23) )
    {
      v6 = *(_QWORD *)(*((_QWORD *)a2 + 20) + 8 * (*((_QWORD *)a2 + 22) & (*((_QWORD *)a2 + 21) - 1LL)));
      v22 = -1;
      v21 = 0;
      v7 = *(_QWORD *)(v6 + 56);
      if ( v7 )
      {
        if ( v7 != v6 )
        {
          v21 = *(std::_Ref_count_base ***)(v6 + 56);
LABEL_38:
          *(_QWORD *)(v6 + 56) = 0;
          goto LABEL_39;
        }
        v21 = (std::_Ref_count_base **)(*(__int64 (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)v7 + 8LL))(
                                         v7,
                                         v20);
        v15 = *(_QWORD *)(v6 + 56);
        if ( v15 )
        {
          LOBYTE(v5) = v15 != v6;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v5);
          goto LABEL_38;
        }
      }
LABEL_39:
      v22 = 0;
      v16 = *(_QWORD *)(*((_QWORD *)a2 + 20) + 8 * (*((_QWORD *)a2 + 22) & (*((_QWORD *)a2 + 21) - 1LL)));
      v17 = *(_QWORD *)(v16 + 56);
      if ( v17 )
      {
        LOBYTE(v5) = v17 != v16;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v5);
        *(_QWORD *)(v16 + 56) = 0;
      }
      v9 = (*((_QWORD *)a2 + 23))-- == 1;
      if ( v9 )
        *((_QWORD *)a2 + 22) = 0;
      else
        ++*((_QWORD *)a2 + 22);
      goto LABEL_26;
    }
    if ( v4 )
      goto LABEL_15;
    goto LABEL_19;
  }
  v10 = *(std::_Ref_count_base ***)(*((_QWORD *)a2 + 25) + 8 * (*((_QWORD *)a2 + 27) & (*((_QWORD *)a2 + 26) - 1LL)));
  v22 = -1;
  *(_OWORD *)v20 = 0;
  v20[0] = *v10;
  v20[1] = v10[1];
  *v10 = 0;
  v10[1] = 0;
  v22 = 1;
  v11 = *(std::_Ref_count_base **)(*(_QWORD *)(*((_QWORD *)a2 + 25)
                                             + 8 * (*((_QWORD *)a2 + 27) & (*((_QWORD *)a2 + 26) - 1LL)))
                                 + 8LL);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v9 = (*((_QWORD *)a2 + 28))-- == 1;
  if ( v9 )
    *((_QWORD *)a2 + 27) = 0;
  else
    ++*((_QWORD *)a2 + 27);
LABEL_26:
  CurrentThread = GetCurrentThread();
  _InterlockedExchange((volatile __int32 *)a2 + 36, GetThreadId(CurrentThread));
  if ( v4 )
    LeaveCriticalSection(v4);
  if ( v22 == 1 )
  {
    v12 = *(void (**)(void))(*(_QWORD *)v20[0] + 8LL);
  }
  else
  {
    if ( v22 )
    {
      v19 = 0;
      pExceptionObject = (std::_Ref_count_base **)&std::bad_variant_access::`vftable';
      throw (std::bad_variant_access *)&pExceptionObject;
    }
    if ( !v21 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v12 = (void (*)(void))*((_QWORD *)*v21 + 2);
  }
  v12();
  _InterlockedDecrement64((volatile signed __int64 *)a2 + 17);
  _InterlockedExchange((volatile __int32 *)a2 + 36, 0);
  if ( !v22 )
    goto LABEL_19;
  if ( v22 != -1 && v20[1] )
    std::_Ref_count_base::_Decref(v20[1]);
}

```

## disassembly

```asm
0x1800100e0  mov     [rsp-8+arg_0], rbx
0x1800100e5  mov     [rsp-8+arg_10], rsi
0x1800100ea  push    rbp
0x1800100eb  push    rdi
0x1800100ec  push    r14
0x1800100ee  lea     rbp, [rsp-47h]
0x1800100f3  sub     rsp, 0A0h
0x1800100fa  mov     rax, cs:__security_cookie
0x180010101  xor     rax, rsp
0x180010104  mov     [rbp+57h+var_20], rax
0x180010108  mov     rbx, rdx
0x18001010b  xor     r14d, r14d
0x18001010e  mov     [rbp+57h+var_38], r14
0x180010112  mov     [rbp+57h+var_30], r14b
0x180010116  lea     rdi, [rdx+8]
0x18001011a  mov     rcx, rdi; lpCriticalSection
0x18001011d  call    cs:__imp_EnterCriticalSection
0x180010123  cmp     dword ptr [rbx], 1
0x180010126  jnz     loc_1800101BA
0x18001012c  cmp     [rbx+0E0h], r14
0x180010133  jnz     loc_180010261
0x180010139  cmp     [rbx+0B8h], r14
0x180010140  jz      loc_180010435
0x180010146  mov     rcx, [rbx+0A8h]
0x18001014d  dec     rcx
0x180010150  and     rcx, [rbx+0B0h]
0x180010157  mov     rax, [rbx+0A0h]
0x18001015e  mov     rsi, [rax+rcx*8]
0x180010162  movsx   rax, [rbp+57h+var_30]
0x180010167  inc     rax
0x18001016a  cmp     rax, 1
0x18001016e  jnz     loc_18001045A
0x180010174  mov     rcx, [rbp+57h+var_38]
0x180010178  test    rcx, rcx
0x18001017b  jz      short loc_180010193
0x18001017d  mov     rax, [rcx]
0x180010180  lea     rdx, [rbp+57h+var_70]
0x180010184  cmp     rcx, rdx
0x180010187  setnz   dl
0x18001018a  mov     rax, [rax+20h]
0x18001018e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010193  mov     [rbp+57h+var_30], 0FFh
0x180010197  mov     [rbp+57h+var_38], r14
0x18001019b  mov     rcx, [rsi+38h]
0x18001019f  test    rcx, rcx
0x1800101a2  jz      loc_1800104AD
0x1800101a8  cmp     rcx, rsi
0x1800101ab  jz      loc_18001047A
0x1800101b1  mov     [rbp+57h+var_38], rcx
0x1800101b5  jmp     loc_1800104A9
0x1800101ba  cmp     [rbx+108h], r14
0x1800101c1  jz      loc_18001031C
0x1800101c7  lea     rax, [rbp+57h+var_70]
0x1800101cb  mov     [rbp+57h+pExceptionObject], rax
0x1800101cf  mov     rcx, [rbx+0F8h]
0x1800101d6  dec     rcx
0x1800101d9  and     rcx, [rbx+100h]
0x1800101e0  mov     rax, [rbx+0F0h]
0x1800101e7  mov     r8, [rax+rcx*8]
0x1800101eb  mov     qword ptr [rbp+57h+var_88], r8
0x1800101ef  movsx   rax, [rbp+57h+var_30]
0x1800101f4  inc     rax
0x1800101f7  cmp     rax, 1
0x1800101fb  jnz     loc_180010443
0x180010201  lea     rax, [rbp+57h+var_70]
0x180010205  mov     [rbp+57h+pExceptionObject], rax
0x180010209  mov     qword ptr [rbp+57h+var_88], r8
0x18001020d  lea     rax, [rbp+57h+var_70]
0x180010211  mov     qword ptr [rbp+57h+var_88+8], rax
0x180010215  movsx   rcx, byte ptr [r8+40h]
0x18001021a  inc     rcx
0x18001021d  lea     rdx, [rbp+57h+pExceptionObject]
0x180010221  call    ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z
0x180010226  mov     rax, [rbx+0F8h]
0x18001022d  dec     rax
0x180010230  and     rax, [rbx+100h]
0x180010237  mov     rcx, [rbx+0F0h]
0x18001023e  mov     rcx, [rcx+rax*8]
0x180010242  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180010247  sub     qword ptr [rbx+108h], 1
0x18001024f  jnz     loc_18001042C
0x180010255  mov     [rbx+100h], r14
0x18001025c  jmp     loc_1800103D7
0x180010261  mov     rcx, [rbx+0D0h]
0x180010268  dec     rcx
0x18001026b  and     rcx, [rbx+0D8h]
0x180010272  mov     rax, [rbx+0C8h]
0x180010279  mov     rsi, [rax+rcx*8]
0x18001027d  movsx   rax, [rbp+57h+var_30]
0x180010282  inc     rax
0x180010285  cmp     rax, 1
0x180010289  jnz     loc_180010512
0x18001028f  mov     rcx, [rbp+57h+var_38]
0x180010293  test    rcx, rcx
0x180010296  jz      short loc_1800102B2
0x180010298  mov     rax, [rcx]
0x18001029b  lea     rdx, [rbp+57h+var_70]
0x18001029f  cmp     rcx, rdx
0x1800102a2  setnz   dl
0x1800102a5  mov     rax, [rax+20h]
0x1800102a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ae  mov     [rbp+57h+var_38], r14
0x1800102b2  mov     [rbp+57h+var_30], 0FFh
0x1800102b6  xorps   xmm0, xmm0
0x1800102b9  movdqa  xmmword ptr [rbp+57h+var_70], xmm0
0x1800102be  mov     rax, [rsi]
0x1800102c1  mov     [rbp+57h+var_70], rax
0x1800102c5  mov     rax, [rsi+8]
0x1800102c9  mov     [rbp+57h+var_70+8], rax
0x1800102cd  mov     [rsi], r14
0x1800102d0  mov     [rsi+8], r14
0x1800102d4  mov     [rbp+57h+var_30], 1
0x1800102d8  mov     rcx, [rbx+0D0h]
0x1800102df  dec     rcx
0x1800102e2  and     rcx, [rbx+0D8h]
0x1800102e9  mov     rax, [rbx+0C8h]
0x1800102f0  mov     rcx, [rax+rcx*8]
0x1800102f4  mov     rcx, [rcx+8]; this
0x1800102f8  test    rcx, rcx
0x1800102fb  jz      short loc_180010302
0x1800102fd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010302  sub     qword ptr [rbx+0E0h], 1
0x18001030a  jz      loc_180010506
0x180010310  inc     qword ptr [rbx+0D8h]
0x180010317  jmp     loc_1800103D7
0x18001031c  test    rdi, rdi
0x18001031f  jz      short loc_18001032A
0x180010321  mov     rcx, rdi; lpCriticalSection
0x180010324  call    cs:__imp_LeaveCriticalSection
0x18001032a  movsx   rax, [rbp+57h+var_30]
0x18001032f  inc     rax
0x180010332  cmp     rax, 1
0x180010336  jz      short loc_180010377
0x180010338  test    rax, rax
0x18001033b  jz      short loc_180010397
0x18001033d  lea     rcx, [rbp+57h+var_70]
0x180010341  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180010346  jmp     short loc_180010397
0x180010348  mov     rcx, [rbp+57h+var_70]
0x18001034c  mov     rax, [rcx]
0x18001034f  mov     rax, [rax+8]
0x180010353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010358  lock dec qword ptr [rbx+88h]
0x180010360  mov     eax, r14d
0x180010363  xchg    eax, [rbx+90h]
0x180010369  movsx   rax, [rbp+57h+var_30]
0x18001036e  inc     rax
0x180010371  cmp     rax, 1
0x180010375  jnz     short loc_1800103BB
0x180010377  mov     rcx, [rbp+57h+var_38]
0x18001037b  test    rcx, rcx
0x18001037e  jz      short loc_180010397
0x180010380  lea     rdx, [rbp+57h+var_70]
0x180010384  cmp     rcx, rdx
0x180010387  mov     rax, [rcx]
0x18001038a  setnz   dl
0x18001038d  mov     rax, [rax+20h]
0x180010391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010396  nop
0x180010397  mov     rcx, [rbp+57h+var_20]
0x18001039b  xor     rcx, rsp; StackCookie
0x18001039e  call    __security_check_cookie
0x1800103a3  lea     r11, [rsp+0B0h+var_10]
0x1800103ab  mov     rbx, [r11+20h]
0x1800103af  mov     rsi, [r11+30h]
0x1800103b3  mov     rsp, r11
0x1800103b6  pop     r14
0x1800103b8  pop     rdi
0x1800103b9  pop     rbp
0x1800103ba  retn
0x1800103bb  test    rax, rax
0x1800103be  jz      short loc_180010397
0x1800103c0  mov     rcx, [rbp+57h+var_70+8]; this
0x1800103c4  test    rcx, rcx
0x1800103c7  jz      short loc_180010397
0x1800103c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800103ce  jmp     short loc_180010397
0x1800103d0  inc     qword ptr [rbx+0B0h]
0x1800103d7  call    cs:__imp_GetCurrentThread
0x1800103dd  mov     rcx, rax; Thread
0x1800103e0  call    cs:__imp_GetThreadId
0x1800103e6  xchg    eax, [rbx+90h]
0x1800103ec  test    rdi, rdi
0x1800103ef  jnz     short loc_180010415
0x1800103f1  movzx   eax, [rbp+57h+var_30]
0x1800103f5  cmp     al, 1
0x1800103f7  jz      loc_180010348
0x1800103fd  test    al, al
0x1800103ff  jnz     loc_180010537
0x180010405  mov     rcx, [rbp+57h+var_38]
0x180010409  test    rcx, rcx
0x18001040c  jnz     short loc_180010420
0x18001040e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180010414  int     3; Trap to Debugger
0x180010415  mov     rcx, rdi; lpCriticalSection
0x180010418  call    cs:__imp_LeaveCriticalSection
0x18001041e  jmp     short loc_1800103F1
0x180010420  mov     rax, [rcx]
0x180010423  mov     rax, [rax+10h]
0x180010427  jmp     loc_180010353
0x18001042c  inc     qword ptr [rbx+100h]
0x180010433  jmp     short loc_1800103D7
0x180010435  test    rdi, rdi
0x180010438  jz      loc_18001032A
0x18001043e  jmp     loc_180010321
0x180010443  lea     rcx, [rbp+57h+pExceptionObject]
0x180010447  test    rax, rax
0x18001044a  jnz     loc_180010529
0x180010450  call    ??$?RU?$_Tagged@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@$0?0@std@@@_lambda_1_@?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV23@@Z@QEBA?A_PU?$_Tagged@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@$0?0@3@@Z
0x180010455  jmp     loc_180010226
0x18001045a  test    rax, rax
0x18001045d  jz      loc_180010193
0x180010463  mov     rcx, [rbp+57h+var_70+8]; this
0x180010467  test    rcx, rcx
0x18001046a  jz      loc_180010193
0x180010470  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010475  jmp     loc_180010193
0x18001047a  mov     rax, [rcx]
0x18001047d  lea     rdx, [rbp+57h+var_70]
0x180010481  mov     rax, [rax+8]
0x180010485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001048a  mov     [rbp+57h+var_38], rax
0x18001048e  mov     rcx, [rsi+38h]
0x180010492  test    rcx, rcx
0x180010495  jz      short loc_1800104AD
0x180010497  mov     rax, [rcx]
0x18001049a  cmp     rcx, rsi
0x18001049d  setnz   dl
0x1800104a0  mov     rax, [rax+20h]
0x1800104a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104a9  mov     [rsi+38h], r14
0x1800104ad  mov     [rbp+57h+var_30], r14b
0x1800104b1  mov     rcx, [rbx+0A8h]
0x1800104b8  dec     rcx
0x1800104bb  and     rcx, [rbx+0B0h]
0x1800104c2  mov     rax, [rbx+0A0h]
0x1800104c9  mov     rsi, [rax+rcx*8]
0x1800104cd  mov     rcx, [rsi+38h]
0x1800104d1  test    rcx, rcx
0x1800104d4  jz      short loc_1800104EC
0x1800104d6  mov     rax, [rcx]
0x1800104d9  cmp     rcx, rsi
0x1800104dc  setnz   dl
0x1800104df  mov     rax, [rax+20h]
0x1800104e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104e8  mov     [rsi+38h], r14
0x1800104ec  sub     qword ptr [rbx+0B8h], 1
0x1800104f4  jnz     loc_1800103D0
0x1800104fa  mov     [rbx+0B0h], r14
0x180010501  jmp     loc_1800103D7
0x180010506  mov     [rbx+0D8h], r14
0x18001050d  jmp     loc_1800103D7
0x180010512  test    rax, rax
0x180010515  jz      loc_1800102B2
0x18001051b  lea     rcx, [rbp+57h+var_70]
0x18001051f  call    ??_G?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAAPEAXI@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::`scalar deleting destructor'(uint)
0x180010524  jmp     loc_1800102B2
0x180010529  lea     rdx, [rbp+57h+var_70]
0x18001052d  call    ??$?RU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@std@@@_lambda_1_@?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV23@@Z@QEBA?A_PU?$_Tagged@AEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@$00@3@@Z
0x180010532  jmp     loc_180010226
0x180010537  xorps   xmm0, xmm0
0x18001053a  movups  [rbp+57h+var_88], xmm0
0x18001053e  lea     rax, ??_7bad_variant_access@std@@6B@; const std::bad_variant_access::`vftable'
0x180010545  mov     [rbp+57h+pExceptionObject], rax
0x180010549  lea     rdx, _TI2?AVbad_variant_access@std@@; pThrowInfo
0x180010550  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180010554  call    _CxxThrowException_0
```
