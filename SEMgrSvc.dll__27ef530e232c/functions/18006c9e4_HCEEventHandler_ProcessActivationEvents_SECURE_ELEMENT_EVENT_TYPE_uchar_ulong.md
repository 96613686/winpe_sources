# HCEEventHandler::ProcessActivationEvents(_SECURE_ELEMENT_EVENT_TYPE,uchar *,ulong)

- ea: `0x18006c9e4`
- end: `0x18006ce3e`
- name: `?ProcessActivationEvents@HCEEventHandler@@QEAAJW4_SECURE_ELEMENT_EVENT_TYPE@@PEAEK@Z`
- size: `1114`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006c4a0`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x1800049c4`
- `0x18000584c`
- `0x180067bdc`
- `0x18006be64`
- `0x18006c048`
- `0x18006c28c`
- `0x18006c9e4`
- `0x18006ce44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006ca9b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006ca9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cbd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cbd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cb8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006cb8e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006cb28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006cd51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006cb28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006cd51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006cc41`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006cc41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HCEEventHandler::ProcessActivationEvents(__int64 a1, __int32 a2, __int16 *a3, unsigned int a4)
{
  bool v6; // cf
  unsigned int Guid; // ebx
  __int16 v8; // r15
  __int64 v9; // r14
  __int64 i; // rbx
  bool v11; // r12
  __int64 v12; // rdx
  void *v13; // rbx
  __int64 v14; // r14
  unsigned __int16 v15; // r9
  unsigned __int16 v16; // dx
  bool v18; // [rsp+30h] [rbp-B8h] BYREF
  _WORD v19[3]; // [rsp+32h] [rbp-B6h] BYREF
  HANDLE h; // [rsp+38h] [rbp-B0h] BYREF
  char v21; // [rsp+40h] [rbp-A8h]
  GUID v22; // [rsp+48h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+60h] [rbp-88h] BYREF
  __m256i v24; // [rsp+70h] [rbp-78h] BYREF
  _WORD *v25; // [rsp+90h] [rbp-58h]
  __int64 v26; // [rsp+98h] [rbp-50h]
  HANDLE *p_h; // [rsp+A0h] [rbp-48h]
  __int64 v28; // [rsp+A8h] [rbp-40h]

  v22 = GUID_NULL;
  if ( a2 == 4 )
    v6 = a4 < 4;
  else
    v6 = a4 < 2;
  if ( v6 )
    return (unsigned int)-2147024809;
  v8 = *a3;
  v9 = a1 + 144;
  for ( i = *(_QWORD *)(a1 + 144); ; i += 56 )
  {
    if ( i == *(_QWORD *)(a1 + 152) )
    {
      v11 = 1;
      pguid = 0;
      memset(&v24, 0, sizeof(v24));
      v25 = 0;
      LOWORD(pguid.Data1) = v8;
      v24.m256i_i8[8] = 0;
      Guid = CoCreateGuid((GUID *)&pguid.Data2);
      if ( (Guid & 0x80000000) != 0 )
        return Guid;
      Guid = 0;
      v24.m256i_i32[1] = a2;
      *(GUID *)((char *)&v24.m256i_u64[1] + 4) = GUID_NULL;
      v25 = 0;
      v12 = *(_QWORD *)(v9 + 8);
      if ( v12 == *(_QWORD *)(v9 + 16) )
      {
        try
        {
          std::vector<HCEEventHandler::ConnectionContext>::_Emplace_reallocate<HCEEventHandler::ConnectionContext const &>(
            v9,
            v12,
            &pguid);
        }
        catch ( std::bad_alloc )
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        *(GUID *)v12 = pguid;
        *(__m256i *)(v12 + 16) = v24;
        *(_QWORD *)(v12 + 48) = v25;
        *(_QWORD *)(v9 + 8) += 56LL;
      }
LABEL_22:
      if ( a2 == 4 )
      {
        if ( (unsigned int)dword_18012F048 > 5
          && (qword_18012F058 & 0x400000000000LL) != 0
          && (qword_18012F060 & 0x400000000000LL) == qword_18012F060 )
        {
          LODWORD(h) = IsDebuggerPresent();
          v19[0] = v8;
          p_h = &h;
          v28 = 4;
          v25 = v19;
          v26 = 2;
          v24.m256i_i64[2] = (__int64)&v22;
          v24.m256i_i64[3] = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_18012F048, &byte_18011D12F, 0, 0, 5, &pguid);
        }
        if ( !v11 )
          return Guid;
        v15 = *(_WORD *)(a1 + 170);
        if ( !v15 )
          return Guid;
        v16 = *(_WORD *)(a1 + 168);
        if ( v16 != v8 )
          return Guid;
        v18 = 0;
        h = 0;
        Guid = HCEEventHandler::ProcessReceive(
                 (HCEEventHandler *)a1,
                 v16,
                 *(unsigned __int8 **)(a1 + 176),
                 v15,
                 &v18,
                 &h);
        if ( (Guid & 0x80000000) != 0 )
          return Guid;
        if ( h )
        {
          if ( *(_BYTE *)(a1 + 200) )
            SetThreadpoolWait(*(PTP_WAIT *)(a1 + 96), h, 0);
          return Guid;
        }
      }
      else
      {
        if ( (unsigned int)dword_18012F048 > 5
          && (qword_18012F058 & 0x400000000000LL) != 0
          && (qword_18012F060 & 0x400000000000LL) == qword_18012F060 )
        {
          v19[0] = v8;
          v25 = v19;
          v26 = 2;
          v24.m256i_i64[2] = (__int64)&v22;
          v24.m256i_i64[3] = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_18012F048, &byte_18011D1E7, 0, 0, 4, &pguid);
        }
        if ( a2 != 5 || !*(_QWORD *)(a1 + 176) || *(_WORD *)(a1 + 168) != v8 )
          return Guid;
      }
      HCEEventHandler::ClearPendingApdu((HCEEventHandler *)a1);
      return Guid;
    }
    if ( v8 == *(_WORD *)i )
      break;
  }
  v18 = 0;
  HCEEventHandler::ClearPendingApdu((HCEEventHandler *)a1);
  if ( *(_BYTE *)(a1 + 200) )
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 96), 0, 0);
  v22 = *(GUID *)(i + 28);
  memmove_0((void *)i, (const void *)(i + 56), *(_QWORD *)(a1 + 152) - (i + 56));
  *(_QWORD *)(a1 + 152) -= 56LL;
  v13 = *(void **)(a1 + 192);
  *(_QWORD *)(a1 + 192) = 0;
  if ( v13 )
  {
    std::vector<AutomaticResponseRule>::~vector<AutomaticResponseRule>(v13);
    operator delete(v13);
  }
  v14 = *(_QWORD *)(a1 + 112);
  h = (HANDLE)(v14 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 48));
  v21 = 1;
  Guid = 0;
  if ( v8 == *(_WORD *)(v14 + 90) )
  {
    Guid = HCEConnectionMgr::CloseConnectionSessionInternal(v14, 0, v19);
    if ( (Guid & 0x80000000) == 0 )
    {
      *(_WORD *)(v14 + 90) = 0;
      *(GUID *)(v14 + 92) = GUID_NULL;
      *(_BYTE *)(v14 + 88) = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 48));
  if ( (Guid & 0x80000000) == 0 )
  {
    v11 = v18;
    goto LABEL_22;
  }
  return Guid;
}

```

## disassembly

```asm
0x18006c9e4  mov     [rsp+arg_8], rbx
0x18006c9e9  mov     [rsp+arg_18], rsi
0x18006c9ee  push    rdi
0x18006c9ef  push    r12
0x18006c9f1  push    r13
0x18006c9f3  push    r14
0x18006c9f5  push    r15
0x18006c9f7  sub     rsp, 0C0h
0x18006c9fe  mov     rax, cs:__security_cookie
0x18006ca05  xor     rax, rsp
0x18006ca08  mov     [rsp+0E8h+var_38], rax
0x18006ca10  mov     r13d, edx
0x18006ca13  mov     rsi, rcx
0x18006ca16  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006ca1d  movdqu  [rsp+0E8h+var_A0], xmm0
0x18006ca23  cmp     edx, 4
0x18006ca26  jnz     short loc_18006CA37
0x18006ca28  cmp     r9d, edx
0x18006ca2b  jnb     short loc_18006CA3D
0x18006ca2d  mov     ebx, 80070057h
0x18006ca32  jmp     loc_18006CE0F
0x18006ca37  cmp     r9d, 2
0x18006ca3b  jmp     short loc_18006CA2B
0x18006ca3d  movzx   r15d, word ptr [r8]
0x18006ca41  lea     r14, [rcx+90h]
0x18006ca48  mov     rbx, [r14]
0x18006ca4b  mov     rax, [rcx+98h]
0x18006ca52  jmp     short loc_18006CA62
0x18006ca54  cmp     r15w, [rbx]
0x18006ca58  jz      loc_18006CB0A
0x18006ca5e  add     rbx, 38h ; '8'
0x18006ca62  cmp     rbx, rax
0x18006ca65  jnz     short loc_18006CA54
0x18006ca67  mov     r12b, 1
0x18006ca6a  xorps   xmm0, xmm0
0x18006ca6d  xor     eax, eax
0x18006ca6f  movups  xmmword ptr [rsp+0E8h+pguid.Data1], xmm0
0x18006ca74  movups  [rsp+0E8h+var_78], xmm0
0x18006ca79  movups  [rsp+0E8h+var_68], xmm0
0x18006ca81  mov     [rsp+0E8h+var_58], rax
0x18006ca89  mov     word ptr [rsp+0E8h+pguid.Data1], r15w
0x18006ca8f  xor     edi, edi
0x18006ca91  mov     byte ptr [rsp+0E8h+var_78+8], dil
0x18006ca96  lea     rcx, [rsp+0E8h+pguid.Data2]; pguid
0x18006ca9b  call    cs:__imp_CoCreateGuid
0x18006caa1  mov     ebx, eax
0x18006caa3  test    eax, eax
0x18006caa5  js      loc_18006CE0F
0x18006caab  mov     ebx, edi
0x18006caad  mov     dword ptr [rsp+0E8h+var_78+4], r13d
0x18006cab2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006cab9  movdqu  [rsp+0E8h+var_78+0Ch], xmm0
0x18006cabf  mov     [rsp+0E8h+var_58], rdi
0x18006cac7  mov     rdx, [r14+8]
0x18006cacb  cmp     rdx, [r14+10h]
0x18006cacf  jz      loc_18006CBE5
0x18006cad5  movups  xmm0, xmmword ptr [rsp+0E8h+pguid.Data1]
0x18006cada  movups  xmmword ptr [rdx], xmm0
0x18006cadd  movups  xmm1, [rsp+0E8h+var_78]
0x18006cae2  movups  xmmword ptr [rdx+10h], xmm1
0x18006cae6  movups  xmm0, [rsp+0E8h+var_68]
0x18006caee  movups  xmmword ptr [rdx+20h], xmm0
0x18006caf2  movsd   xmm1, [rsp+0E8h+var_58]
0x18006cafb  movsd   qword ptr [rdx+30h], xmm1
0x18006cb00  add     qword ptr [r14+8], 38h ; '8'
0x18006cb05  jmp     loc_18006CBF3
0x18006cb0a  xor     edi, edi
0x18006cb0c  mov     [rsp+0E8h+var_B8], dil
0x18006cb11  call    ?ClearPendingApdu@HCEEventHandler@@AEAAXXZ; HCEEventHandler::ClearPendingApdu(void)
0x18006cb16  cmp     [rsi+0C8h], dil
0x18006cb1d  jz      short loc_18006CB2E
0x18006cb1f  xor     r8d, r8d; pftTimeout
0x18006cb22  xor     edx, edx; h
0x18006cb24  mov     rcx, [rsi+60h]; pwa
0x18006cb28  call    cs:__imp_SetThreadpoolWait
0x18006cb2e  movups  xmm0, xmmword ptr [rbx+1Ch]
0x18006cb32  movdqu  [rsp+0E8h+var_A0], xmm0
0x18006cb38  lea     rdx, [rbx+38h]; Src
0x18006cb3c  mov     r8, [rsi+98h]
0x18006cb43  sub     r8, rdx; Size
0x18006cb46  mov     rcx, rbx; void *
0x18006cb49  call    memmove_0
0x18006cb4e  add     qword ptr [rsi+98h], 0FFFFFFFFFFFFFFC8h
0x18006cb56  mov     rbx, [rsi+0C0h]
0x18006cb5d  mov     [rsi+0C0h], rdi
0x18006cb64  test    rbx, rbx
0x18006cb67  jz      short loc_18006CB7E
0x18006cb69  mov     rcx, rbx
0x18006cb6c  call    ??1?$vector@UAutomaticResponseRule@@V?$allocator@UAutomaticResponseRule@@@std@@@std@@QEAA@XZ; std::vector<AutomaticResponseRule>::~vector<AutomaticResponseRule>(void)
0x18006cb71  mov     edx, 40h ; '@'
0x18006cb76  mov     rcx, rbx; Block
0x18006cb79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006cb7e  mov     r14, [rsi+70h]
0x18006cb82  lea     r12, [r14+30h]
0x18006cb86  mov     [rsp+0E8h+h], r12
0x18006cb8b  mov     rcx, r12; lpCriticalSection
0x18006cb8e  call    cs:__imp_EnterCriticalSection
0x18006cb94  mov     [rsp+0E8h+var_A8], 1
0x18006cb99  mov     ebx, edi
0x18006cb9b  cmp     r15w, [r14+5Ah]
0x18006cba0  jnz     short loc_18006CBCD
0x18006cba2  lea     r8, [rsp+0E8h+var_B6]
0x18006cba7  xor     edx, edx
0x18006cba9  mov     rcx, r14
0x18006cbac  call    ?CloseConnectionSessionInternal@HCEConnectionMgr@@AEAAJW4HostSecureElementConnectionDeactivatedReason@@PEA_N@Z; HCEConnectionMgr::CloseConnectionSessionInternal(HostSecureElementConnectionDeactivatedReason,bool *)
0x18006cbb1  mov     ebx, eax
0x18006cbb3  test    eax, eax
0x18006cbb5  js      short loc_18006CBCD
0x18006cbb7  mov     [r14+5Ah], di
0x18006cbbc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006cbc3  movdqu  xmmword ptr [r14+5Ch], xmm0
0x18006cbc9  mov     [r14+58h], dil
0x18006cbcd  mov     rcx, r12; lpCriticalSection
0x18006cbd0  call    cs:__imp_LeaveCriticalSection
0x18006cbd6  test    ebx, ebx
0x18006cbd8  js      loc_18006CE0F
0x18006cbde  mov     r12b, [rsp+0E8h+var_B8]
0x18006cbe3  jmp     short loc_18006CBF3
0x18006cbe5  lea     r8, [rsp+0E8h+pguid]
0x18006cbea  mov     rcx, r14
0x18006cbed  call    ??$_Emplace_reallocate@AEBUConnectionContext@HCEEventHandler@@@?$vector@UConnectionContext@HCEEventHandler@@V?$allocator@UConnectionContext@HCEEventHandler@@@std@@@std@@AEAAPEAUConnectionContext@HCEEventHandler@@QEAU23@AEBU23@@Z; std::vector<HCEEventHandler::ConnectionContext>::_Emplace_reallocate<HCEEventHandler::ConnectionContext const &>(HCEEventHandler::ConnectionContext * const,HCEEventHandler::ConnectionContext const &)
0x18006cbf2  nop
0x18006cbf3  mov     r14d, 4
0x18006cbf9  mov     eax, cs:dword_18012F048
0x18006cbff  cmp     r13d, r14d
0x18006cc02  jnz     loc_18006CD5C
0x18006cc08  cmp     eax, 5
0x18006cc0b  jbe     loc_18006CCC3
0x18006cc11  mov     rdx, cs:qword_18012F060
0x18006cc18  mov     rax, cs:qword_18012F058
0x18006cc1f  mov     rcx, 400000000000h
0x18006cc29  test    rcx, rax
0x18006cc2c  jz      loc_18006CCC3
0x18006cc32  mov     rax, rdx
0x18006cc35  and     rax, rcx
0x18006cc38  cmp     rax, rdx
0x18006cc3b  jnz     loc_18006CCC3
0x18006cc41  call    cs:__imp_IsDebuggerPresent
0x18006cc47  mov     dword ptr [rsp+0E8h+h], eax
0x18006cc4b  mov     [rsp+0E8h+var_B6], r15w
0x18006cc51  lea     rax, [rsp+0E8h+h]
0x18006cc56  mov     [rsp+0E8h+var_48], rax
0x18006cc5e  mov     [rsp+0E8h+var_40], r14
0x18006cc66  lea     rax, [rsp+0E8h+var_B6]
0x18006cc6b  mov     [rsp+0E8h+var_58], rax
0x18006cc73  mov     [rsp+0E8h+var_50], 2
0x18006cc7f  lea     rax, [rsp+0E8h+var_A0]
0x18006cc84  mov     qword ptr [rsp+0E8h+var_68], rax
0x18006cc8c  mov     qword ptr [rsp+0E8h+var_68+8], 10h
0x18006cc98  lea     rax, [rsp+0E8h+pguid]
0x18006cc9d  mov     [rsp+0E8h+var_C0], rax
0x18006cca2  mov     dword ptr [rsp+0E8h+var_C8], 5
0x18006ccaa  xor     r9d, r9d
0x18006ccad  xor     r8d, r8d
0x18006ccb0  lea     rdx, byte_18011D12F
0x18006ccb7  lea     rcx, dword_18012F048
0x18006ccbe  call    _tlgWriteTransfer_EventWriteTransfer
0x18006ccc3  test    r12b, r12b
0x18006ccc6  jz      loc_18006CE0F
0x18006cccc  movzx   r9d, word ptr [rsi+0AAh]; unsigned __int16
0x18006ccd4  test    r9w, r9w
0x18006ccd8  jz      loc_18006CE0F
0x18006ccde  movzx   edx, word ptr [rsi+0A8h]; unsigned __int16
0x18006cce5  cmp     dx, r15w
0x18006cce9  jnz     loc_18006CE0F
0x18006ccef  mov     [rsp+0E8h+var_B8], dil
0x18006ccf4  mov     [rsp+0E8h+h], rdi
0x18006ccf9  lea     rax, [rsp+0E8h+h]
0x18006ccfe  mov     [rsp+0E8h+var_C0], rax; void **
0x18006cd03  lea     rax, [rsp+0E8h+var_B8]
0x18006cd08  mov     [rsp+0E8h+var_C8], rax; bool *
0x18006cd0d  mov     r8, [rsi+0B0h]; unsigned __int8 *
0x18006cd14  mov     rcx, rsi; this
0x18006cd17  call    ?ProcessReceive@HCEEventHandler@@AEAAJGPEAEGPEA_NPEAPEAX@Z; HCEEventHandler::ProcessReceive(ushort,uchar *,ushort,bool *,void * *)
0x18006cd1c  mov     ebx, eax
0x18006cd1e  test    eax, eax
0x18006cd20  js      loc_18006CE0F
0x18006cd26  mov     rdx, [rsp+0E8h+h]; h
0x18006cd2b  test    rdx, rdx
0x18006cd2e  jnz     short loc_18006CD3D
0x18006cd30  mov     rcx, rsi; this
0x18006cd33  call    ?ClearPendingApdu@HCEEventHandler@@AEAAXXZ; HCEEventHandler::ClearPendingApdu(void)
0x18006cd38  jmp     loc_18006CE0F
0x18006cd3d  cmp     [rsi+0C8h], dil
0x18006cd44  jz      loc_18006CE0F
0x18006cd4a  xor     r8d, r8d; pftTimeout
0x18006cd4d  mov     rcx, [rsi+60h]; pwa
0x18006cd51  call    cs:__imp_SetThreadpoolWait
0x18006cd57  jmp     loc_18006CE0F
0x18006cd5c  cmp     eax, 5
0x18006cd5f  jbe     loc_18006CDED
0x18006cd65  mov     rdx, cs:qword_18012F060
0x18006cd6c  mov     rax, cs:qword_18012F058
0x18006cd73  mov     rcx, 400000000000h
0x18006cd7d  test    rcx, rax
0x18006cd80  jz      short loc_18006CDED
0x18006cd82  mov     rax, rdx
0x18006cd85  and     rax, rcx
0x18006cd88  cmp     rax, rdx
0x18006cd8b  jnz     short loc_18006CDED
0x18006cd8d  mov     [rsp+0E8h+var_B6], r15w
0x18006cd93  lea     rax, [rsp+0E8h+var_B6]
0x18006cd98  mov     [rsp+0E8h+var_58], rax
0x18006cda0  mov     [rsp+0E8h+var_50], 2
0x18006cdac  lea     rax, [rsp+0E8h+var_A0]
0x18006cdb1  mov     qword ptr [rsp+0E8h+var_68], rax
0x18006cdb9  mov     qword ptr [rsp+0E8h+var_68+8], 10h
0x18006cdc5  lea     rax, [rsp+0E8h+pguid]
0x18006cdca  mov     [rsp+0E8h+var_C0], rax
0x18006cdcf  mov     dword ptr [rsp+0E8h+var_C8], r14d
0x18006cdd4  xor     r9d, r9d
0x18006cdd7  xor     r8d, r8d
0x18006cdda  lea     rdx, byte_18011D1E7
0x18006cde1  lea     rcx, dword_18012F048
0x18006cde8  call    _tlgWriteTransfer_EventWriteTransfer
0x18006cded  cmp     r13d, 5
0x18006cdf1  jnz     short loc_18006CE0F
0x18006cdf3  cmp     [rsi+0B0h], rdi
0x18006cdfa  jz      short loc_18006CE0F
0x18006cdfc  cmp     [rsi+0A8h], r15w
0x18006ce04  jnz     short loc_18006CE0F
0x18006ce06  jmp     loc_18006CD30
0x18006ce0b  mov     ebx, dword ptr [rsp+0E8h+h]
0x18006ce0f  mov     eax, ebx
0x18006ce11  mov     rcx, [rsp+0E8h+var_38]
0x18006ce19  xor     rcx, rsp; StackCookie
0x18006ce1c  call    __security_check_cookie
0x18006ce21  lea     r11, [rsp+0E8h+var_28]
0x18006ce29  mov     rbx, [r11+38h]
0x18006ce2d  mov     rsi, [r11+48h]
0x18006ce31  mov     rsp, r11
0x18006ce34  pop     r15
0x18006ce36  pop     r14
0x18006ce38  pop     r13
0x18006ce3a  pop     r12
0x18006ce3c  pop     rdi
0x18006ce3d  retn
```
