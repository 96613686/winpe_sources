# ServiceHandlerEx(ulong,ulong,void *,void *)

- ea: `0x18000fdc0`
- end: `0x1800100b5`
- name: `?ServiceHandlerEx@@YAKKKPEAX0@Z`
- size: `757`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000dba0`
- `0x18000fdc0`
- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010056`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010056`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ff6e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ff6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ServiceHandlerEx(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  _BYTE *v5; // rax
  char v6; // bl
  unsigned int v7; // esi
  int v9; // [rsp+20h] [rbp-68h]
  int v10; // [rsp+28h] [rbp-60h]

  v5 = WPP_GLOBAL_Control;
  v6 = 1;
  LOBYTE(dwEventType) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwEventType,
      (_DWORD)lpEventData,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v5 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  switch ( dwControl )
  {
    case 1u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)v5 + 2),
          dwEventType,
          (_DWORD)lpEventData,
          *((_QWORD *)v5 + 5),
          v9,
          v10,
          16,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      }
      goto LABEL_61;
    case 2u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_63;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)v5 + 2),
        dwEventType,
        (_DWORD)lpEventData,
        *((_QWORD *)v5 + 5),
        v9,
        v10,
        15,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
LABEL_62:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_63;
    case 3u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( !(_BYTE)dwEventType && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_63;
      LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)v5 + 2),
        dwEventType,
        (_DWORD)lpEventData,
        *((_QWORD *)v5 + 5),
        v9,
        v10,
        14,
        (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      goto LABEL_62;
    case 4u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)v5 + 2),
          dwEventType,
          (_DWORD)lpEventData,
          *((_QWORD *)v5 + 5),
          v9,
          v10,
          13,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      }
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      goto LABEL_62;
    case 5u:
      LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 4u;
      if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)v5 + 2),
          dwEventType,
          (_DWORD)lpEventData,
          *((_QWORD *)v5 + 5),
          v9,
          v10,
          17,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
      }
LABEL_61:
      BthServSetState(3u);
      SetEvent(Globals);
      goto LABEL_62;
    case 0xEu:
      if ( !hLibModule )
        goto LABEL_63;
      ((void (__fastcall *)(__int64, __int64, LPVOID, LPVOID))qword_180044BB8)(2, dwEventType, lpEventData, lpContext);
      goto LABEL_62;
  }
  LOBYTE(dwEventType) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 3u;
  if ( (_BYTE)dwEventType || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(lpEventData) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v5 + 2),
      dwEventType,
      (_DWORD)lpEventData,
      *((_QWORD *)v5 + 5),
      v9,
      v10,
      18,
      (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v7 = 120;
LABEL_63:
  if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 5u )
    v6 = 0;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v5 + 2),
      v6,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v5 + 5));
  return v7;
}

```

## disassembly

```asm
0x18000fdc0  push    rbx
0x18000fdc2  push    rbp
0x18000fdc3  push    rsi
0x18000fdc4  push    rdi
0x18000fdc5  push    r14
0x18000fdc7  push    r15
0x18000fdc9  sub     rsp, 58h
0x18000fdcd  mov     edi, ecx
0x18000fdcf  mov     rax, cs:WPP_GLOBAL_Control
0x18000fdd6  lea     rbp, WPP_GLOBAL_Control
0x18000fddd  mov     ebx, 1
0x18000fde2  cmp     rax, rbp
0x18000fde5  jz      short loc_18000FDF1
0x18000fde7  cmp     byte ptr [rax+19h], 5
0x18000fdeb  jb      short loc_18000FDF1
0x18000fded  mov     dl, bl
0x18000fdef  jmp     short loc_18000FDF3
0x18000fdf1  xor     dl, dl
0x18000fdf3  lea     r14, WPP_RECORDER_INITIALIZED
0x18000fdfa  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fe01  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000fe08  setnz   r8b
0x18000fe0c  test    dl, dl
0x18000fe0e  jnz     short loc_18000FE15
0x18000fe10  test    r8b, r8b
0x18000fe13  jz      short loc_18000FE35
0x18000fe15  mov     r9, [rax+28h]
0x18000fe19  mov     rcx, [rax+10h]
0x18000fe1d  mov     [rsp+88h+var_50], r15
0x18000fe22  mov     [rsp+88h+var_58], 0Ch
0x18000fe29  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000fe2e  mov     rax, cs:WPP_GLOBAL_Control
0x18000fe35  xor     esi, esi
0x18000fe37  mov     ecx, edi
0x18000fe39  sub     ecx, ebx
0x18000fe3b  jz      loc_180010003
0x18000fe41  sub     ecx, ebx
0x18000fe43  jz      loc_18000FFC8
0x18000fe49  sub     ecx, ebx
0x18000fe4b  jz      loc_18000FF79
0x18000fe51  sub     ecx, ebx
0x18000fe53  jz      loc_18000FF1A
0x18000fe59  sub     ecx, ebx
0x18000fe5b  jz      short loc_18000FED8
0x18000fe5d  cmp     ecx, 9
0x18000fe60  jz      short loc_18000FEB5
0x18000fe62  cmp     rax, rbp
0x18000fe65  jz      short loc_18000FE71
0x18000fe67  cmp     byte ptr [rax+19h], 3
0x18000fe6b  jb      short loc_18000FE71
0x18000fe6d  mov     dl, bl
0x18000fe6f  jmp     short loc_18000FE73
0x18000fe71  xor     dl, dl
0x18000fe73  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fe7a  setnz   r8b
0x18000fe7e  test    dl, dl
0x18000fe80  jnz     short loc_18000FE87
0x18000fe82  test    r8b, r8b
0x18000fe85  jz      short loc_18000FEAB
0x18000fe87  mov     r9, [rax+28h]
0x18000fe8b  mov     rcx, [rax+10h]
0x18000fe8f  mov     dword ptr [rsp+88h+var_40], edi
0x18000fe93  mov     [rsp+88h+var_50], r15
0x18000fe98  mov     [rsp+88h+var_58], 12h
0x18000fe9f  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000fea4  mov     rax, cs:WPP_GLOBAL_Control
0x18000feab  mov     esi, 78h ; 'x'
0x18000feb0  jmp     loc_180010063
0x18000feb5  cmp     cs:hLibModule, rsi
0x18000febc  jz      loc_180010063
0x18000fec2  mov     rax, cs:qword_180044BB8
0x18000fec9  mov     ecx, 2
0x18000fece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fed3  jmp     loc_18001005C
0x18000fed8  cmp     rax, rbp
0x18000fedb  jz      short loc_18000FEE7
0x18000fedd  cmp     byte ptr [rax+19h], 4
0x18000fee1  jb      short loc_18000FEE7
0x18000fee3  mov     dl, bl
0x18000fee5  jmp     short loc_18000FEE9
0x18000fee7  xor     dl, dl
0x18000fee9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fef0  setnz   r8b
0x18000fef4  test    dl, dl
0x18000fef6  jnz     short loc_18000FF01
0x18000fef8  test    r8b, r8b
0x18000fefb  jz      loc_180010045
0x18000ff01  mov     dword ptr [rsp+88h+var_40], 5
0x18000ff09  mov     [rsp+88h+var_50], r15
0x18000ff0e  mov     [rsp+88h+var_58], 11h
0x18000ff15  jmp     loc_180010038
0x18000ff1a  cmp     rax, rbp
0x18000ff1d  jz      short loc_18000FF29
0x18000ff1f  cmp     byte ptr [rax+19h], 4
0x18000ff23  jb      short loc_18000FF29
0x18000ff25  mov     dl, bl
0x18000ff27  jmp     short loc_18000FF2B
0x18000ff29  xor     dl, dl
0x18000ff2b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000ff32  setnz   r8b
0x18000ff36  test    dl, dl
0x18000ff38  jnz     short loc_18000FF3F
0x18000ff3a  test    r8b, r8b
0x18000ff3d  jz      short loc_18000FF60
0x18000ff3f  mov     r9, [rax+28h]
0x18000ff43  mov     rcx, [rax+10h]
0x18000ff47  mov     dword ptr [rsp+88h+var_40], 4
0x18000ff4f  mov     [rsp+88h+var_50], r15
0x18000ff54  mov     [rsp+88h+var_58], 0Dh
0x18000ff5b  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000ff60  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000ff67  lea     rdx, ServiceStatus; lpServiceStatus
0x18000ff6e  call    cs:__imp_SetServiceStatus
0x18000ff74  jmp     loc_18001005C
0x18000ff79  cmp     rax, rbp
0x18000ff7c  jz      short loc_18000FF88
0x18000ff7e  cmp     byte ptr [rax+19h], 4
0x18000ff82  jb      short loc_18000FF88
0x18000ff84  mov     dl, bl
0x18000ff86  jmp     short loc_18000FF8A
0x18000ff88  xor     dl, dl
0x18000ff8a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000ff91  setnz   r8b
0x18000ff95  test    dl, dl
0x18000ff97  jnz     short loc_18000FFA2
0x18000ff99  test    r8b, r8b
0x18000ff9c  jz      loc_180010063
0x18000ffa2  mov     dword ptr [rsp+88h+var_40], 3
0x18000ffaa  mov     [rsp+88h+var_50], r15
0x18000ffaf  mov     [rsp+88h+var_58], 0Eh
0x18000ffb6  mov     r9, [rax+28h]
0x18000ffba  mov     rcx, [rax+10h]
0x18000ffbe  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000ffc3  jmp     loc_18001005C
0x18000ffc8  cmp     rax, rbp
0x18000ffcb  jz      short loc_18000FFD7
0x18000ffcd  cmp     byte ptr [rax+19h], 4
0x18000ffd1  jb      short loc_18000FFD7
0x18000ffd3  mov     dl, bl
0x18000ffd5  jmp     short loc_18000FFD9
0x18000ffd7  xor     dl, dl
0x18000ffd9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000ffe0  setnz   r8b
0x18000ffe4  test    dl, dl
0x18000ffe6  jnz     short loc_18000FFED
0x18000ffe8  test    r8b, r8b
0x18000ffeb  jz      short loc_180010063
0x18000ffed  mov     dword ptr [rsp+88h+var_40], 2
0x18000fff5  mov     [rsp+88h+var_50], r15
0x18000fffa  mov     [rsp+88h+var_58], 0Fh
0x180010001  jmp     short loc_18000FFB6
0x180010003  cmp     rax, rbp
0x180010006  jz      short loc_180010012
0x180010008  cmp     byte ptr [rax+19h], 4
0x18001000c  jb      short loc_180010012
0x18001000e  mov     dl, bl
0x180010010  jmp     short loc_180010014
0x180010012  xor     dl, dl
0x180010014  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001001b  setnz   r8b
0x18001001f  test    dl, dl
0x180010021  jnz     short loc_180010028
0x180010023  test    r8b, r8b
0x180010026  jz      short loc_180010045
0x180010028  mov     dword ptr [rsp+88h+var_40], ebx
0x18001002c  mov     [rsp+88h+var_50], r15
0x180010031  mov     [rsp+88h+var_58], 10h
0x180010038  mov     r9, [rax+28h]
0x18001003c  mov     rcx, [rax+10h]
0x180010040  call    WPP_RECORDER_AND_TRACE_SF_sd
0x180010045  mov     ecx, 3; unsigned int
0x18001004a  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x18001004f  mov     rcx, cs:?Globals@@3VBthServGlobals@@A; hEvent
0x180010056  call    cs:__imp_SetEvent
0x18001005c  mov     rax, cs:WPP_GLOBAL_Control
0x180010063  cmp     rax, rbp
0x180010066  jz      short loc_18001006E
0x180010068  cmp     byte ptr [rax+19h], 5
0x18001006c  jnb     short loc_180010070
0x18001006e  xor     bl, bl
0x180010070  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010077  setnz   r8b
0x18001007b  test    bl, bl
0x18001007d  jnz     short loc_180010084
0x18001007f  test    r8b, r8b
0x180010082  jz      short loc_1800100A6
0x180010084  mov     r9, [rax+28h]
0x180010088  mov     dl, bl
0x18001008a  mov     ecx, esi
0x18001008c  mov     [rsp+88h+var_40], rcx
0x180010091  mov     rcx, [rax+10h]
0x180010095  mov     [rsp+88h+var_50], r15
0x18001009a  mov     [rsp+88h+var_58], 13h
0x1800100a1  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800100a6  mov     eax, esi
0x1800100a8  add     rsp, 58h
0x1800100ac  pop     r15
0x1800100ae  pop     r14
0x1800100b0  pop     rdi
0x1800100b1  pop     rsi
0x1800100b2  pop     rbp
0x1800100b3  pop     rbx
0x1800100b4  retn
```
