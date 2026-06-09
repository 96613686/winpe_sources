# CILogWriteAsynch::SetCheckpoint(_ULARGE_INTEGER,CAsynchSupport *,_ULARGE_INTEGER *)

- ea: `0x180005710`
- end: `0x18000596c`
- name: `?SetCheckpoint@CILogWriteAsynch@@UEAAJT_ULARGE_INTEGER@@PEAVCAsynchSupport@@PEAT2@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CILogWriteAsynch *__hidden this, union _ULARGE_INTEGER, struct CAsynchSupport *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004708`
- `0x180005710`
- `0x180008090`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005920`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005920`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CILogWriteAsynch::SetCheckpoint(
        CILogWriteAsynch *this,
        union _ULARGE_INTEGER a2,
        struct CAsynchSupport *a3,
        union _ULARGE_INTEGER *a4)
{
  __int64 v7; // r9
  unsigned int v8; // r14d
  struct _STRMTBL *Stream; // rsi
  __int64 v10; // r15
  __int64 v11; // rax
  int v12; // ebx
  union _ULARGE_INTEGER *v13; // rcx
  union _ULARGE_INTEGER v14; // r12
  __int64 v15; // r9
  unsigned int v16; // r8d
  unsigned int v17; // eax
  int v18; // r10d
  int v19; // ecx
  __int64 v20; // rdx
  unsigned int v22; // [rsp+20h] [rbp-58h] BYREF
  ulong v23[3]; // [rsp+24h] [rbp-54h] BYREF
  __int64 v24; // [rsp+30h] [rbp-48h]

  if ( a2.QuadPart )
  {
    if ( a3 )
    {
      v7 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v7 + 620) - a2.HighPart <= 1
        && a2.HighPart <= *(_DWORD *)(v7 + 620)
        && (*(unsigned int (__fastcall **)(__int64, _QWORD, union _ULARGE_INTEGER))(*(_QWORD *)(v7 + 144) + 24LL))(
             v7 + 144,
             *(_QWORD *)(v7 + 616),
             a2) != 1 )
      {
        v8 = 0;
        Stream = CILogStorage::GetStream(
                   (CILogStorage *)(*((_QWORD *)this + 2) + 96LL),
                   *(_DWORD *)(*((_QWORD *)this + 1) + 328LL));
        if ( !Stream )
          return (unsigned int)-2147418113;
        try
        {
          v10 = *((_QWORD *)this + 2) + 304LL;
          v23[1] = 1;
          v24 = v10;
          (**(void (__fastcall ***)(__int64))v10)(v10);
          *(union _ULARGE_INTEGER *)((char *)Stream + 8 * (unsigned __int16)(*((_WORD *)Stream + 9))++ + 28) = a2;
          v11 = *((unsigned __int16 *)Stream + 9);
          v12 = 2;
          if ( (_WORD)v11 == 2 )
          {
            LOWORD(v11) = 0;
            *((_WORD *)Stream + 9) = 0;
          }
          else if ( (unsigned __int16)v11 >= 2u )
          {
            v13 = (union _ULARGE_INTEGER *)((char *)Stream + 8 * v11 + 12);
            goto LABEL_13;
          }
          v13 = (union _ULARGE_INTEGER *)((char *)Stream + 8 * (unsigned __int16)v11 + 28);
LABEL_13:
          v14 = *v13;
          if ( v13->QuadPart )
          {
            *(union _ULARGE_INTEGER *)(*(_QWORD *)((char *)Stream + 20) + 592LL) = v14;
            v8 = CLogMgr::_SetLowWater(*((CLogMgr **)this + 2), v14, 0);
          }
          v15 = *((_QWORD *)this + 2);
          if ( *(_DWORD *)(v15 + 360) >= 0x19u )
          {
            v8 = -2147430396;
          }
          else
          {
            if ( *(_DWORD *)(v15 + 380) )
            {
              *(_DWORD *)(v15 + 380) = 0;
              v16 = 0;
              *(_DWORD *)(*((_QWORD *)this + 2) + 376LL) = 0;
            }
            else
            {
              v17 = *(_DWORD *)(v15 + 376);
              if ( v17 >= 0x18 )
              {
                v18 = 1;
                v16 = 0;
                do
                {
                  if ( v16 >= 0x19 )
                    break;
                  v19 = *(_QWORD *)(*(_QWORD *)(v15 + 368) + 16LL * v16 + 8) != 0 ? v18 : 0;
                  v18 = v19;
                  if ( *(_QWORD *)(*(_QWORD *)(v15 + 368) + 16LL * v16 + 8) )
                    ++v16;
                }
                while ( v19 );
              }
              else
              {
                do
                {
                  *(_DWORD *)(*((_QWORD *)this + 2) + 376LL) = v17 + 1;
                  --v12;
                }
                while ( v12 );
                v16 = *(_DWORD *)(*((_QWORD *)this + 2) + 376LL);
              }
            }
            ++*(_DWORD *)(*((_QWORD *)this + 2) + 360LL);
            v20 = 2LL * v16;
            *(union _ULARGE_INTEGER *)(*(_QWORD *)(*((_QWORD *)this + 2) + 368LL) + 8 * v20) = v14;
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 368LL) + 8 * v20 + 8) = a3;
            _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 2) + 388LL));
            SetEvent(*(HANDLE *)(*((_QWORD *)this + 2) + 552LL));
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        }
        catch ( long v22 )
        {
          return v22;
        }
        catch ( ulong v23 )
        {
          return v23[0];
        }
        return v8;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180005710  push    rbx
0x180005712  push    rsi
0x180005713  push    rdi
0x180005714  push    r12
0x180005716  push    r13
0x180005718  push    r14
0x18000571a  push    r15
0x18000571c  sub     rsp, 40h
0x180005720  mov     r13, r8
0x180005723  mov     rbx, rdx
0x180005726  mov     rdi, rcx
0x180005729  test    rdx, rdx
0x18000572c  jz      loc_180005957
0x180005732  test    r8, r8
0x180005735  jz      loc_180005957
0x18000573b  mov     r9, [rcx+10h]
0x18000573f  mov     edx, [r9+26Ch]
0x180005746  mov     rcx, rbx
0x180005749  shr     rcx, 20h
0x18000574d  mov     eax, edx
0x18000574f  sub     eax, ecx
0x180005751  mov     r12d, 1
0x180005757  cmp     eax, r12d
0x18000575a  ja      loc_180005957
0x180005760  cmp     ecx, edx
0x180005762  ja      loc_180005957
0x180005768  lea     rcx, [r9+90h]
0x18000576f  mov     rax, [rcx]
0x180005772  mov     r8, rbx
0x180005775  mov     rdx, [r9+268h]
0x18000577c  mov     rax, [rax+18h]
0x180005780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005785  cmp     eax, r12d
0x180005788  jz      loc_180005957
0x18000578e  xor     r14d, r14d
0x180005791  mov     rdx, [rdi+8]
0x180005795  mov     rcx, [rdi+10h]
0x180005799  add     rcx, 60h ; '`'; this
0x18000579d  mov     edx, [rdx+148h]; unsigned int
0x1800057a3  call    ?GetStream@CILogStorage@@AEAAPEAU_STRMTBL@@K@Z; CILogStorage::GetStream(ulong)
0x1800057a8  mov     rsi, rax
0x1800057ab  test    rax, rax
0x1800057ae  jz      loc_18000594C
0x1800057b4  mov     r15, [rdi+10h]
0x1800057b8  add     r15, 130h
0x1800057bf  mov     [rsp+78h+var_50], r12d
0x1800057c4  mov     [rsp+78h+var_48], r15
0x1800057c9  mov     rcx, [r15]
0x1800057cc  mov     rax, [rcx]
0x1800057cf  mov     rcx, r15
0x1800057d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d7  nop
0x1800057d8  movzx   eax, word ptr [rsi+12h]
0x1800057dc  mov     [rsi+rax*8+1Ch], rbx
0x1800057e1  add     [rsi+12h], r12w
0x1800057e6  movzx   eax, word ptr [rsi+12h]
0x1800057ea  lea     ebx, [r12+1]
0x1800057ef  cmp     ax, bx
0x1800057f2  jnz     short loc_1800057FC
0x1800057f4  xor     eax, eax
0x1800057f6  mov     [rsi+12h], ax
0x1800057fa  jmp     short loc_1800057FE
0x1800057fc  jnb     short loc_18000580B
0x1800057fe  movzx   eax, ax
0x180005801  lea     rcx, [rsi+1Ch]
0x180005805  lea     rcx, [rcx+rax*8]
0x180005809  jmp     short loc_180005816
0x18000580b  lea     rcx, ds:0Ch[rax*8]
0x180005813  add     rcx, rsi
0x180005816  mov     r12, [rcx]
0x180005819  test    r12, r12
0x18000581c  jz      short loc_18000583B
0x18000581e  mov     rax, [rsi+14h]
0x180005822  mov     [rax+250h], r12
0x180005829  xor     r8d, r8d; int
0x18000582c  mov     rdx, r12; union _ULARGE_INTEGER
0x18000582f  mov     rcx, [rdi+10h]; this
0x180005833  call    ?_SetLowWater@CLogMgr@@QEAAJT_ULARGE_INTEGER@@H@Z; CLogMgr::_SetLowWater(_ULARGE_INTEGER,int)
0x180005838  mov     r14d, eax
0x18000583b  mov     r9, [rdi+10h]
0x18000583f  cmp     dword ptr [r9+168h], 19h
0x180005847  jnb     loc_180005928
0x18000584d  cmp     dword ptr [r9+17Ch], 0
0x180005855  jz      short loc_180005872
0x180005857  mov     dword ptr [r9+17Ch], 0
0x180005862  xor     r8d, r8d
0x180005865  mov     rax, [rdi+10h]
0x180005869  mov     [rax+178h], r8d
0x180005870  jmp     short loc_1800058DB
0x180005872  mov     eax, [r9+178h]
0x180005879  cmp     eax, 18h
0x18000587c  jnb     short loc_18000589D
0x18000587e  lea     ecx, [rax+1]
0x180005881  mov     rax, [rdi+10h]
0x180005885  mov     [rax+178h], ecx
0x18000588b  sub     ebx, 1
0x18000588e  jnz     short loc_180005881
0x180005890  mov     rax, [rdi+10h]
0x180005894  mov     r8d, [rax+178h]
0x18000589b  jmp     short loc_1800058DB
0x18000589d  mov     r10d, 1
0x1800058a3  xor     r8d, r8d
0x1800058a6  cmp     r8d, 19h
0x1800058aa  jnb     short loc_1800058DB
0x1800058ac  mov     ecx, r8d
0x1800058af  add     rcx, rcx
0x1800058b2  mov     rax, [r9+170h]
0x1800058b9  mov     rdx, [rax+rcx*8+8]
0x1800058be  mov     rax, rdx
0x1800058c1  neg     rax
0x1800058c4  sbb     ecx, ecx
0x1800058c6  and     ecx, r10d
0x1800058c9  mov     r10d, ecx
0x1800058cc  lea     eax, [r8+1]
0x1800058d0  test    rdx, rdx
0x1800058d3  cmovnz  r8d, eax
0x1800058d7  test    ecx, ecx
0x1800058d9  jnz     short loc_1800058A6
0x1800058db  mov     rax, [rdi+10h]
0x1800058df  inc     dword ptr [rax+168h]
0x1800058e5  mov     edx, r8d
0x1800058e8  add     rdx, rdx
0x1800058eb  mov     rax, [rdi+10h]
0x1800058ef  mov     rcx, [rax+170h]
0x1800058f6  mov     [rcx+rdx*8], r12
0x1800058fa  mov     rax, [rdi+10h]
0x1800058fe  mov     rcx, [rax+170h]
0x180005905  mov     [rcx+rdx*8+8], r13
0x18000590a  mov     rax, [rdi+10h]
0x18000590e  lock inc dword ptr [rax+184h]
0x180005915  mov     rcx, [rdi+10h]
0x180005919  mov     rcx, [rcx+228h]; hEvent
0x180005920  call    cs:__imp_SetEvent
0x180005926  jmp     short loc_18000592E
0x180005928  mov     r14d, 8000D004h
0x18000592e  mov     rax, [r15]
0x180005931  mov     rcx, r15
0x180005934  mov     rax, [rax+8]
0x180005938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593d  nop
0x18000593e  jmp     short loc_180005952
0x180005940  mov     eax, [rsp+78h+var_58]
0x180005944  jmp     short loc_18000594A
0x180005946  mov     eax, [rsp+78h+var_54]
0x18000594a  jmp     short loc_18000595C
0x18000594c  mov     r14d, 8000FFFFh
0x180005952  mov     eax, r14d
0x180005955  jmp     short loc_18000595C
0x180005957  mov     eax, 80070057h
0x18000595c  add     rsp, 40h
0x180005960  pop     r15
0x180005962  pop     r14
0x180005964  pop     r13
0x180005966  pop     r12
0x180005968  pop     rdi
0x180005969  pop     rsi
0x18000596a  pop     rbx
0x18000596b  retn
```
