# SrpLoadPlugin

- ea: `0x14002459c`
- end: `0x140024970`
- name: `SrpLoadPlugin`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x14002bf44`

## callees

- `0x140001e4c`
- `0x1400032bc`
- `0x140006f40`
- `0x140024530`
- `0x14002459c`
- `0x140024c50`
- `0x140024d70`
- `0x140029714`
- `0x1400328b0`
- `0x140032a50`
- `0x140036380`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002490d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002494d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002490d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002494d`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14002479e`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14002479e`
- `ntoskrnl!ZwClose` at `0x140024925`
- `ntoskrnl!ZwClose` at `0x140024925`

## string_xrefs

- `0x140024793`: `\SystemRoot\System32\AppLocker\{........-....-....-....-............}.Policy`
- `0x14002481e`: `\SystemRoot\System32\AppLocker\{%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%02x%02x%02x}.Policy`

## pseudocode

```c
__int64 __fastcall SrpLoadPlugin(__int64 a1, _QWORD *a2, _QWORD *a3, unsigned int *a4, _DWORD *a5)
{
  char *v5; // r13
  unsigned int v6; // esi
  int PluginFileName; // ebx
  char v8; // r14
  __int64 v9; // r10
  __int64 v10; // rdi
  unsigned int v11; // r11d
  __int64 v12; // rcx
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int i; // edx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r9
  char *v21; // rax
  unsigned int *v22; // r12
  unsigned int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r9
  __int128 v27; // xmm0
  __int64 v29; // [rsp+28h] [rbp-B1h]
  __int64 v30; // [rsp+30h] [rbp-A9h]
  __int64 v31; // [rsp+38h] [rbp-A1h]
  __int64 v32; // [rsp+40h] [rbp-99h]
  __int64 v33; // [rsp+48h] [rbp-91h]
  __int64 v34; // [rsp+50h] [rbp-89h]
  __int64 v35; // [rsp+58h] [rbp-81h]
  __int64 v36; // [rsp+60h] [rbp-79h]
  __int64 v37; // [rsp+68h] [rbp-71h]
  __int64 v38; // [rsp+70h] [rbp-69h]
  unsigned int v39; // [rsp+78h] [rbp-61h]
  unsigned int v40; // [rsp+78h] [rbp-61h]
  unsigned int v41; // [rsp+7Ch] [rbp-5Dh]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-59h] BYREF
  int v43; // [rsp+90h] [rbp-49h]
  HANDLE Handle; // [rsp+98h] [rbp-41h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+A8h] [rbp-31h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-21h] BYREF
  struct _UNICODE_STRING v47; // [rsp+C8h] [rbp-11h]
  __int128 v48; // [rsp+D8h] [rbp-1h]
  char v49; // [rsp+138h] [rbp+5Fh]

  Handle = 0;
  DestinationString = 0;
  *a5 = 0;
  v5 = 0;
  v6 = 0;
  v46 = 0;
  v41 = 0;
  v47 = 0;
  *a3 = 0;
  v48 = 0;
  *a4 = 0;
  UnicodeString = 0;
  PluginFileName = SrpGetPluginFileName((__int64)&UnicodeString);
  if ( PluginFileName >= 0 )
  {
    PluginFileName = SrpOpenFile(&UnicodeString, &Handle);
    if ( PluginFileName >= 0 )
    {
      PluginFileName = AiGetPlugins(Handle);
      v43 = PluginFileName;
      if ( PluginFileName >= 0 )
      {
        if ( MEMORY[0x1C] )
        {
          v8 = 0;
          v9 = MEMORY[8];
          v10 = MEMORY[0x10];
          v39 = 0;
          v11 = 0;
          if ( !MEMORY[0xC] )
            goto LABEL_33;
          v12 = EdpPluginGuid;
          v13 = 0;
          do
          {
            v14 = *(_QWORD *)v9 - v12;
            if ( *(_QWORD *)v9 == v12 )
              v14 = *(_QWORD *)(v9 + 8) - 0x36F6D035FB531A99LL;
            if ( !v14 )
            {
              v15 = *(unsigned int *)(v9 + 32);
              v16 = v10 + 28LL * *(unsigned int *)(v9 + 28);
              for ( i = 0; i < (unsigned int)v15; ++i )
              {
                v18 = *(_QWORD *)v16 - *a2;
                if ( *(_QWORD *)v16 == *a2 )
                  v18 = *(_QWORD *)(v16 + 8) - a2[1];
                if ( !v18 )
                {
                  *a5 = 0;
                  v19 = *(_QWORD *)v16 - 0x4896EF1A58125A50LL;
                  if ( *(_QWORD *)v16 == 0x4896EF1A58125A50LL )
                    v19 = *(_QWORD *)(v16 + 8) - 0x6CCAB39AC6D657BALL;
                  v8 = 1;
                  if ( !v19 )
                    v13 = 1;
                  LOBYTE(v15) = v13;
                  AiSetAttributes(a5, *(unsigned int *)(v16 + 16), v15);
                  v6 = *(_DWORD *)(v20 + 24);
                  v39 = *(_DWORD *)(v20 + 20);
                  break;
                }
                v16 += 28;
              }
              v12 = EdpPluginGuid;
            }
            ++v11;
            v9 += 36;
          }
          while ( v11 < MEMORY[0xC] );
          v49 = v13;
          PluginFileName = v43;
          v5 = 0;
          v41 = v6;
          if ( !v8 )
          {
LABEL_33:
            PluginFileName = -1073741275;
            goto LABEL_35;
          }
          if ( v6 )
          {
            v21 = (char *)AiAlloc(32LL * v6);
            v5 = v21;
            if ( !v21
              || (memset(v21, 0, 32LL * v6),
                  !RtlCreateUnicodeString(
                     &DestinationString,
                     L"\\SystemRoot\\System32\\AppLocker\\{........-....-....-....-............}.Policy")) )
            {
              PluginFileName = -1073741801;
              goto LABEL_35;
            }
            v22 = (unsigned int *)(MEMORY[0x18] + 16LL * v39);
            v23 = 0;
            while ( 1 )
            {
              v40 = v23;
              if ( v23 >= v6 )
                break;
              LODWORD(v38) = *((unsigned __int8 *)v22 + 15);
              LODWORD(v37) = *((unsigned __int8 *)v22 + 14);
              LODWORD(v36) = *((unsigned __int8 *)v22 + 13);
              LODWORD(v35) = *((unsigned __int8 *)v22 + 12);
              LODWORD(v34) = *((unsigned __int8 *)v22 + 11);
              LODWORD(v33) = *((unsigned __int8 *)v22 + 10);
              LODWORD(v32) = *((unsigned __int8 *)v22 + 9);
              LODWORD(v31) = *((unsigned __int8 *)v22 + 8);
              LODWORD(v30) = *((unsigned __int16 *)v22 + 3);
              LODWORD(v29) = *((unsigned __int16 *)v22 + 2);
              PluginFileName = RtlStringCchPrintfW(
                                 DestinationString.Buffer,
                                 (unsigned __int64)DestinationString.MaximumLength >> 1,
                                 L"\\SystemRoot\\System32\\AppLocker\\{%08x-%04hx-%04hx-%02x%02x-%02x%02x%02x%02x%02x%02x}.Policy",
                                 *v22,
                                 v29,
                                 v30,
                                 v31,
                                 v32,
                                 v33,
                                 v34,
                                 v35,
                                 v36,
                                 v37,
                                 v38);
              if ( PluginFileName < 0 )
                goto LABEL_35;
              v47 = DestinationString;
              v46 = 0u;
              v48 = 0;
              PluginFileName = SrpLoadPolicy(&v46);
              if ( PluginFileName < 0 )
                goto LABEL_35;
              LOBYTE(v24) = v49;
              AiSetAttributes(a5, *(unsigned int *)(*((_QWORD *)&v48 + 1) + 28LL), v24);
              v6 = v41;
              v25 = 32LL * v40;
              v23 = v40 + 1;
              *(_QWORD *)&v5[v25 + 24] = v26;
              *(_DWORD *)&v5[v25 + 20] = 1;
              *(_DWORD *)&v5[v25 + 16] = 0;
              v27 = *(_OWORD *)v22;
              v22 += 4;
              *(_OWORD *)&v5[v25] = v27;
            }
          }
        }
        *a3 = v5;
        v5 = 0;
        *a4 = v6;
      }
    }
  }
LABEL_35:
  RtlFreeUnicodeString(&DestinationString);
  if ( Handle )
    ZwClose(Handle);
  AiFree(0);
  if ( v5 )
    SrpFreePlugin(v5, v41);
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)PluginFileName;
}

```

## disassembly

```asm
0x14002459c  mov     rax, rsp
0x14002459f  mov     [rax+20h], r9
0x1400245a3  mov     [rax+18h], r8
0x1400245a7  mov     [rax+10h], rdx
0x1400245ab  mov     [rax+8], rcx
0x1400245af  push    rbp
0x1400245b0  push    rbx
0x1400245b1  push    rsi
0x1400245b2  push    rdi
0x1400245b3  push    r12
0x1400245b5  push    r13
0x1400245b7  push    r14
0x1400245b9  push    r15
0x1400245bb  lea     rbp, [rax-57h]
0x1400245bf  sub     rsp, 0E8h
0x1400245c6  mov     rax, [rbp+4Fh+arg_20]
0x1400245ca  lea     rcx, [rbp+4Fh+UnicodeString]
0x1400245ce  xor     r12d, r12d
0x1400245d1  xorps   xmm0, xmm0
0x1400245d4  mov     [rbp+4Fh+Handle], r12
0x1400245d8  mov     r15d, r12d
0x1400245db  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400245df  mov     [rax], r12d
0x1400245e2  mov     r13d, r12d
0x1400245e5  mov     [rbp+4Fh+arg_0], r12
0x1400245e9  mov     esi, r12d
0x1400245ec  movups  [rbp+4Fh+var_70], xmm0
0x1400245f0  mov     [rbp+4Fh+var_AC], r12d
0x1400245f4  movups  [rbp+4Fh+var_60], xmm0
0x1400245f8  mov     [r8], r12
0x1400245fb  movups  [rbp+4Fh+var_50], xmm0
0x1400245ff  mov     [r9], r12d
0x140024602  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x140024606  call    SrpGetPluginFileName
0x14002460b  mov     ebx, eax
0x14002460d  test    eax, eax
0x14002460f  js      loc_140024909
0x140024615  lea     rdx, [rbp+4Fh+Handle]
0x140024619  lea     rcx, [rbp+4Fh+UnicodeString]
0x14002461d  call    SrpOpenFile
0x140024622  mov     ebx, eax
0x140024624  test    eax, eax
0x140024626  js      loc_140024909
0x14002462c  mov     rcx, [rbp+4Fh+Handle]; Handle
0x140024630  lea     rdx, [rbp+4Fh+arg_0]
0x140024634  call    AiGetPlugins
0x140024639  mov     r15, [rbp+4Fh+arg_0]
0x14002463d  mov     ebx, eax
0x14002463f  mov     [rbp+4Fh+var_98], eax
0x140024642  test    eax, eax
0x140024644  js      loc_140024909
0x14002464a  cmp     [r15+1Ch], r12d
0x14002464e  jbe     loc_1400248F9
0x140024654  mov     r10d, [r15+8]
0x140024658  mov     r14b, r12b
0x14002465b  mov     edi, [r15+10h]
0x14002465f  add     r10, r15
0x140024662  add     rdi, r15
0x140024665  mov     [rbp+4Fh+var_B0], r12d
0x140024669  mov     r11d, r12d
0x14002466c  mov     byte ptr [rbp+4Fh+arg_0], r12b
0x140024670  cmp     [r15+0Ch], r12d
0x140024674  jbe     loc_1400248EF
0x14002467a  mov     r12, cs:qword_14000DD38
0x140024681  mov     rcx, cs:EdpPluginGuid
0x140024688  mov     r13, [rbp+4Fh+arg_20]
0x14002468c  mov     ebx, dword ptr [rbp+4Fh+arg_0]
0x14002468f  mov     rax, [r10]
0x140024692  sub     rax, rcx
0x140024695  jnz     short loc_14002469E
0x140024697  mov     rax, [r10+8]
0x14002469b  sub     rax, r12
0x14002469e  test    rax, rax
0x1400246a1  jnz     loc_140024735
0x1400246a7  mov     eax, [r10+1Ch]
0x1400246ab  mov     r8d, [r10+20h]
0x1400246af  imul    r9, rax, 1Ch
0x1400246b3  add     r9, rdi
0x1400246b6  xor     edx, edx
0x1400246b8  cmp     edx, r8d
0x1400246bb  jnb     short loc_14002472E
0x1400246bd  mov     rax, [rbp+4Fh+arg_8]
0x1400246c1  mov     rcx, [r9]
0x1400246c4  sub     rcx, [rax]
0x1400246c7  jnz     short loc_1400246D1
0x1400246c9  mov     rcx, [r9+8]
0x1400246cd  sub     rcx, [rax+8]
0x1400246d1  test    rcx, rcx
0x1400246d4  jz      short loc_1400246DE
0x1400246d6  inc     edx
0x1400246d8  add     r9, 1Ch
0x1400246dc  jmp     short loc_1400246B8
0x1400246de  mov     dword ptr [r13+0], 0
0x1400246e6  mov     rax, [r9]
0x1400246e9  sub     rax, cs:qword_14000C378
0x1400246f0  jnz     short loc_1400246FD
0x1400246f2  mov     rax, [r9+8]
0x1400246f6  sub     rax, cs:qword_14000C380
0x1400246fd  mov     edx, [r9+10h]
0x140024701  test    rax, rax
0x140024704  movzx   ebx, bl
0x140024707  mov     r14d, 1
0x14002470d  cmovz   ebx, r14d
0x140024711  mov     rcx, r13
0x140024714  mov     r8b, bl
0x140024717  call    AiSetAttributes
0x14002471c  mov     eax, [r9+14h]
0x140024720  mov     esi, [r9+18h]
0x140024724  mov     r12, cs:qword_14000DD38
0x14002472b  mov     [rbp+4Fh+var_B0], eax
0x14002472e  mov     rcx, cs:EdpPluginGuid
0x140024735  inc     r11d
0x140024738  add     r10, 24h ; '$'
0x14002473c  cmp     r11d, [r15+0Ch]
0x140024740  jb      loc_14002468F
0x140024746  xor     r12d, r12d
0x140024749  mov     dword ptr [rbp+4Fh+arg_0], ebx
0x14002474c  mov     ebx, [rbp+4Fh+var_98]
0x14002474f  mov     r13d, r12d
0x140024752  mov     [rbp+4Fh+var_AC], esi
0x140024755  test    r14b, r14b
0x140024758  jz      loc_1400248EF
0x14002475e  test    esi, esi
0x140024760  jz      loc_1400248F9
0x140024766  mov     edi, esi
0x140024768  shl     rdi, 5
0x14002476c  mov     rcx, rdi
0x14002476f  call    AiAlloc
0x140024774  mov     r13, rax
0x140024777  test    rax, rax
0x14002477a  jnz     short loc_140024786
0x14002477c  mov     ebx, 0C0000017h
0x140024781  jmp     loc_140024909
0x140024786  mov     r8, rdi; Size
0x140024789  xor     edx, edx; Val
0x14002478b  mov     rcx, r13; void *
0x14002478e  call    memset
0x140024793  lea     rdx, aSystemrootSyst_1; "\\SystemRoot\\System32\\AppLocker\\{..."...
0x14002479a  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14002479e  call    cs:__imp_RtlCreateUnicodeString
0x1400247a5  nop     dword ptr [rax+rax+00h]
0x1400247aa  test    al, al
0x1400247ac  jz      short loc_14002477C
0x1400247ae  mov     eax, [r15+18h]
0x1400247b2  mov     r12d, [rbp+4Fh+var_B0]
0x1400247b6  add     rax, r15
0x1400247b9  shl     r12, 4
0x1400247bd  add     r12, rax
0x1400247c0  xor     eax, eax
0x1400247c2  mov     [rbp+4Fh+var_B0], eax
0x1400247c5  cmp     eax, esi
0x1400247c7  jnb     loc_1400248F6
0x1400247cd  movzx   ecx, byte ptr [r12+0Eh]
0x1400247d3  movzx   r8d, byte ptr [r12+0Dh]
0x1400247d9  movzx   r9d, byte ptr [r12+0Ch]
0x1400247df  movzx   eax, byte ptr [r12+0Fh]
0x1400247e5  movzx   r10d, byte ptr [r12+0Bh]
0x1400247eb  movzx   r11d, byte ptr [r12+0Ah]
0x1400247f1  movzx   ebx, byte ptr [r12+9]
0x1400247f7  movzx   edi, byte ptr [r12+8]
0x1400247fd  movzx   esi, word ptr [r12+6]
0x140024803  movzx   edx, [rbp+4Fh+DestinationString.MaximumLength]
0x140024807  movzx   r14d, word ptr [r12+4]
0x14002480d  mov     [rsp+68h], eax
0x140024811  mov     dword ptr [rsp+120h+var_C0], ecx
0x140024815  mov     rcx, [rbp+4Fh+DestinationString.Buffer]; pszDest
0x140024819  mov     dword ptr [rsp+120h+var_C8], r8d
0x14002481e  lea     r8, aSystemrootSyst_0; "\\SystemRoot\\System32\\AppLocker\\{%08"...
0x140024825  mov     dword ptr [rsp+120h+var_D0], r9d
0x14002482a  mov     r9d, [r12]
0x14002482e  mov     dword ptr [rsp+120h+var_D8], r10d
0x140024833  mov     dword ptr [rsp+120h+var_E0], r11d
0x140024838  mov     dword ptr [rsp+120h+var_E8], ebx
0x14002483c  mov     dword ptr [rsp+120h+var_F0], edi
0x140024840  mov     dword ptr [rsp+120h+var_F8], esi
0x140024844  shr     rdx, 1; cchDest
0x140024847  mov     dword ptr [rsp+120h+var_100], r14d
0x14002484c  call    RtlStringCchPrintfW
0x140024851  mov     ebx, eax
0x140024853  test    eax, eax
0x140024855  js      loc_140024909
0x14002485b  movzx   eax, [rbp+4Fh+DestinationString.Length]
0x14002485f  lea     rcx, [rbp+4Fh+var_70]
0x140024863  mov     word ptr [rbp+4Fh+var_60], ax
0x140024867  xorps   xmm0, xmm0
0x14002486a  movzx   eax, [rbp+4Fh+DestinationString.MaximumLength]
0x14002486e  mov     word ptr [rbp+4Fh+var_60+2], ax
0x140024872  mov     eax, dword ptr [rbp+4Fh+DestinationString+4]
0x140024875  mov     dword ptr [rbp+4Fh+var_60+4], eax
0x140024878  mov     rax, [rbp+4Fh+DestinationString.Buffer]
0x14002487c  mov     qword ptr [rbp+4Fh+var_60+8], rax
0x140024880  mov     qword ptr [rbp+4Fh+var_70], 0
0x140024888  mov     qword ptr [rbp+4Fh+var_70+8], 0
0x140024890  movdqu  [rbp+4Fh+var_50], xmm0
0x140024895  call    SrpLoadPolicy
0x14002489a  mov     ebx, eax
0x14002489c  test    eax, eax
0x14002489e  js      short loc_140024909
0x1400248a0  mov     r9, qword ptr [rbp+4Fh+var_50+8]
0x1400248a4  mov     r8b, byte ptr [rbp+4Fh+arg_0]
0x1400248a8  mov     rcx, [rbp+4Fh+arg_20]
0x1400248ac  mov     edx, [r9+1Ch]
0x1400248b0  call    AiSetAttributes
0x1400248b5  mov     eax, [rbp+4Fh+var_B0]
0x1400248b8  mov     edx, 1
0x1400248bd  mov     esi, [rbp+4Fh+var_AC]
0x1400248c0  mov     ecx, eax
0x1400248c2  shl     rcx, 5
0x1400248c6  add     eax, edx
0x1400248c8  mov     [rcx+r13+18h], r9
0x1400248cd  mov     [rcx+r13+14h], edx
0x1400248d2  mov     dword ptr [rcx+r13+10h], 0
0x1400248db  movups  xmm0, xmmword ptr [r12]
0x1400248e0  add     r12, 10h
0x1400248e4  movdqu  xmmword ptr [rcx+r13], xmm0
0x1400248ea  jmp     loc_1400247C2
0x1400248ef  mov     ebx, 0C0000225h
0x1400248f4  jmp     short loc_140024909
0x1400248f6  xor     r12d, r12d
0x1400248f9  mov     rax, [rbp+4Fh+arg_10]
0x1400248fd  mov     [rax], r13
0x140024900  mov     r13, r12
0x140024903  mov     rax, [rbp+4Fh+arg_18]
0x140024907  mov     [rax], esi
0x140024909  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14002490d  call    cs:__imp_RtlFreeUnicodeString
0x140024914  nop     dword ptr [rax+rax+00h]
0x140024919  mov     rax, [rbp+4Fh+Handle]
0x14002491d  test    rax, rax
0x140024920  jz      short loc_140024931
0x140024922  mov     rcx, rax; Handle
0x140024925  call    cs:__imp_ZwClose
0x14002492c  nop     dword ptr [rax+rax+00h]
0x140024931  mov     rcx, r15
0x140024934  call    AiFree
0x140024939  test    r13, r13
0x14002493c  jz      short loc_140024949
0x14002493e  mov     edx, [rbp+4Fh+var_AC]
0x140024941  mov     rcx, r13
0x140024944  call    SrpFreePlugin
0x140024949  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14002494d  call    cs:__imp_RtlFreeUnicodeString
0x140024954  nop     dword ptr [rax+rax+00h]
0x140024959  mov     eax, ebx
0x14002495b  add     rsp, 0E8h
0x140024962  pop     r15
0x140024964  pop     r14
0x140024966  pop     r13
0x140024968  pop     r12
0x14002496a  pop     rdi
0x14002496b  pop     rsi
0x14002496c  pop     rbx
0x14002496d  pop     rbp
0x14002496e  retn
```
