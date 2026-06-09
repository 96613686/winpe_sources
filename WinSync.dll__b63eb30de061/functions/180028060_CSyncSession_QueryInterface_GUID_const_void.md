# CSyncSession::QueryInterface(_GUID const &,void * *)

- ea: `0x180028060`
- end: `0x180028299`
- name: `?QueryInterface@CSyncSession@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `569`
- prototype: `__int64 __fastcall(LPUNKNOWN punkOuter, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180030df0`
- `0x180030e00`
- `0x180030e10`
- `0x180030e20`
- `0x180030e30`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180028060`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002826d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002826d`

## pseudocode

```c
__int64 __fastcall CSyncSession::QueryInterface(LPUNKNOWN punkOuter, const struct _GUID *a2, void **a3)
{
  PVOID *v6; // rcx
  unsigned int FreeThreadedMarshaler; // ebp
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  LPUNKNOWN v19; // rsi

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_24b986413345305da18a80c41c45e189_Traceguids,
      "CSyncSession::QueryInterface");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  FreeThreadedMarshaler = -2147467261;
  if ( a3 )
  {
    *a3 = 0;
    FreeThreadedMarshaler = -2147467262;
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v8 )
    {
      v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncSession.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncSession.Data1 )
        v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncSession.Data4;
      if ( v9 )
      {
        v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISupportErrorInfo.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISupportErrorInfo.Data1 )
          v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISupportErrorInfo.Data4;
        if ( v10 )
        {
          v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncCallback.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncCallback.Data1 )
            v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncCallback.Data4;
          if ( !v12 )
            goto LABEL_22;
          v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncCallback2.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncCallback2.Data1 )
            v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncCallback2.Data4;
          if ( v13 )
          {
            v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncConstraintCallback.Data1;
            if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncConstraintCallback.Data1 )
              v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncConstraintCallback.Data4;
            if ( v14 )
            {
              v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncSessionExtendedErrorInfo.Data1;
              if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncSessionExtendedErrorInfo.Data1 )
                v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncSessionExtendedErrorInfo.Data4;
              if ( v15 )
              {
                v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISyncDataConversionControl.Data1;
                if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISyncDataConversionControl.Data1 )
                  v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISyncDataConversionControl.Data4;
                if ( v16 )
                {
                  v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMarshal.Data1;
                  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMarshal.Data1 )
                    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMarshal.Data4;
                  if ( !v18 )
                  {
                    v19 = punkOuter + 10;
                    if ( !punkOuter[10].lpVtbl )
                      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(punkOuter, (LPUNKNOWN *)&punkOuter[10]);
                    if ( v19->lpVtbl )
                      FreeThreadedMarshaler = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, const struct _GUID *, void **))v19->lpVtbl->QueryInterface)(
                                                v19->lpVtbl,
                                                a2,
                                                a3);
                  }
                  goto LABEL_38;
                }
                v11 = (unsigned __int64)&punkOuter[5];
              }
              else
              {
                v11 = (unsigned __int64)&punkOuter[3];
              }
            }
            else
            {
              v11 = (unsigned __int64)&punkOuter[4];
            }
          }
          else
          {
LABEL_22:
            v11 = (unsigned __int64)&punkOuter[2];
          }
        }
        else
        {
          v11 = (unsigned __int64)&punkOuter[1];
        }
        punkOuter = (LPUNKNOWN)(v11 & -(__int64)(punkOuter != 0));
      }
    }
    if ( punkOuter )
    {
      *a3 = punkOuter;
      ((void (__fastcall *)(LPUNKNOWN))punkOuter->lpVtbl->AddRef)(punkOuter);
      FreeThreadedMarshaler = 0;
    }
LABEL_38:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      29,
      (unsigned int)WPP_24b986413345305da18a80c41c45e189_Traceguids,
      (unsigned int)"CSyncSession::QueryInterface",
      FreeThreadedMarshaler);
  return FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180028060  push    rbx
0x180028062  push    rbp
0x180028063  push    rsi
0x180028064  push    rdi
0x180028065  push    r14
0x180028067  push    r15
0x180028069  sub     rsp, 38h
0x18002806d  mov     r14, r8
0x180028070  mov     rdi, rdx
0x180028073  mov     rbx, rcx
0x180028076  mov     rcx, cs:WPP_GLOBAL_Control
0x18002807d  lea     r15, WPP_GLOBAL_Control
0x180028084  cmp     rcx, r15
0x180028087  jz      short loc_1800280B8
0x180028089  test    byte ptr [rcx+1Ch], 4
0x18002808d  jz      short loc_1800280B8
0x18002808f  cmp     byte ptr [rcx+19h], 5
0x180028093  jb      short loc_1800280B8
0x180028095  mov     rcx, [rcx+10h]
0x180028099  lea     r9, aCsyncsessionQu; "CSyncSession::QueryInterface"
0x1800280a0  mov     edx, 1Ch
0x1800280a5  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x1800280ac  call    WPP_SF_s
0x1800280b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280b8  mov     ebp, 80004003h
0x1800280bd  test    r14, r14
0x1800280c0  jz      loc_180028202
0x1800280c6  mov     qword ptr [r14], 0
0x1800280cd  mov     ebp, 80004002h
0x1800280d2  mov     rax, [rdi]
0x1800280d5  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800280dc  jnz     short loc_1800280E9
0x1800280de  mov     rax, [rdi+8]
0x1800280e2  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800280e9  test    rax, rax
0x1800280ec  jz      loc_1800281E2
0x1800280f2  mov     rax, [rdi]
0x1800280f5  sub     rax, qword ptr cs:IID_ISyncSession.Data1
0x1800280fc  jnz     short loc_180028109
0x1800280fe  mov     rax, [rdi+8]
0x180028102  sub     rax, qword ptr cs:IID_ISyncSession.Data4
0x180028109  test    rax, rax
0x18002810c  jz      loc_1800281E2
0x180028112  mov     rax, [rdi]
0x180028115  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x18002811c  jnz     short loc_180028129
0x18002811e  mov     rax, [rdi+8]
0x180028122  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x180028129  test    rax, rax
0x18002812c  jnz     short loc_180028137
0x18002812e  lea     rax, [rbx+8]
0x180028132  jmp     loc_1800281D9
0x180028137  mov     rax, [rdi]
0x18002813a  sub     rax, qword ptr cs:IID_ISyncCallback.Data1
0x180028141  jnz     short loc_18002814E
0x180028143  mov     rax, [rdi+8]
0x180028147  sub     rax, qword ptr cs:IID_ISyncCallback.Data4
0x18002814e  test    rax, rax
0x180028151  jz      short loc_18002816F
0x180028153  mov     rax, [rdi]
0x180028156  sub     rax, qword ptr cs:IID_ISyncCallback2.Data1
0x18002815d  jnz     short loc_18002816A
0x18002815f  mov     rax, [rdi+8]
0x180028163  sub     rax, qword ptr cs:IID_ISyncCallback2.Data4
0x18002816a  test    rax, rax
0x18002816d  jnz     short loc_180028175
0x18002816f  lea     rax, [rbx+10h]
0x180028173  jmp     short loc_1800281D9
0x180028175  mov     rax, [rdi]
0x180028178  sub     rax, qword ptr cs:IID_ISyncConstraintCallback.Data1
0x18002817f  jnz     short loc_18002818C
0x180028181  mov     rax, [rdi+8]
0x180028185  sub     rax, qword ptr cs:IID_ISyncConstraintCallback.Data4
0x18002818c  test    rax, rax
0x18002818f  jnz     short loc_180028197
0x180028191  lea     rax, [rbx+20h]
0x180028195  jmp     short loc_1800281D9
0x180028197  mov     rax, [rdi]
0x18002819a  sub     rax, qword ptr cs:IID_ISyncSessionExtendedErrorInfo.Data1
0x1800281a1  jnz     short loc_1800281AE
0x1800281a3  mov     rax, [rdi+8]
0x1800281a7  sub     rax, qword ptr cs:IID_ISyncSessionExtendedErrorInfo.Data4
0x1800281ae  test    rax, rax
0x1800281b1  jnz     short loc_1800281B9
0x1800281b3  lea     rax, [rbx+18h]
0x1800281b7  jmp     short loc_1800281D9
0x1800281b9  mov     rax, [rdi]
0x1800281bc  sub     rax, qword ptr cs:IID_ISyncDataConversionControl.Data1
0x1800281c3  jnz     short loc_1800281D0
0x1800281c5  mov     rax, [rdi+8]
0x1800281c9  sub     rax, qword ptr cs:IID_ISyncDataConversionControl.Data4
0x1800281d0  test    rax, rax
0x1800281d3  jnz     short loc_180028242
0x1800281d5  lea     rax, [rbx+28h]
0x1800281d9  neg     rbx
0x1800281dc  sbb     rbx, rbx
0x1800281df  and     rbx, rax
0x1800281e2  test    rbx, rbx
0x1800281e5  jz      short loc_1800281FB
0x1800281e7  mov     [r14], rbx
0x1800281ea  mov     rcx, rbx
0x1800281ed  mov     rax, [rbx]
0x1800281f0  mov     rax, [rax+8]
0x1800281f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f9  xor     ebp, ebp
0x1800281fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028202  cmp     rcx, r15
0x180028205  jz      short loc_180028233
0x180028207  test    byte ptr [rcx+1Ch], 4
0x18002820b  jz      short loc_180028233
0x18002820d  cmp     byte ptr [rcx+19h], 5
0x180028211  jb      short loc_180028233
0x180028213  mov     rcx, [rcx+10h]
0x180028217  lea     r9, aCsyncsessionQu; "CSyncSession::QueryInterface"
0x18002821e  mov     edx, 1Dh
0x180028223  mov     [rsp+68h+var_48], ebp
0x180028227  lea     r8, WPP_24b986413345305da18a80c41c45e189_Traceguids
0x18002822e  call    WPP_SF_sD
0x180028233  mov     eax, ebp
0x180028235  add     rsp, 38h
0x180028239  pop     r15
0x18002823b  pop     r14
0x18002823d  pop     rdi
0x18002823e  pop     rsi
0x18002823f  pop     rbp
0x180028240  pop     rbx
0x180028241  retn
0x180028242  mov     rax, [rdi]
0x180028245  sub     rax, qword ptr cs:IID_IMarshal.Data1
0x18002824c  jnz     short loc_180028259
0x18002824e  mov     rax, [rdi+8]
0x180028252  sub     rax, qword ptr cs:IID_IMarshal.Data4
0x180028259  test    rax, rax
0x18002825c  jnz     short loc_1800281FB
0x18002825e  lea     rsi, [rbx+50h]
0x180028262  cmp     [rsi], rax
0x180028265  jnz     short loc_180028275
0x180028267  mov     rdx, rsi; ppunkMarshal
0x18002826a  mov     rcx, rbx; punkOuter
0x18002826d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180028273  mov     ebp, eax
0x180028275  mov     rcx, [rsi]
0x180028278  test    rcx, rcx
0x18002827b  jz      loc_1800281FB
0x180028281  mov     rax, [rcx]
0x180028284  mov     r8, r14
0x180028287  mov     rdx, rdi
0x18002828a  mov     rax, [rax]
0x18002828d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028292  mov     ebp, eax
0x180028294  jmp     loc_1800281FB
```
