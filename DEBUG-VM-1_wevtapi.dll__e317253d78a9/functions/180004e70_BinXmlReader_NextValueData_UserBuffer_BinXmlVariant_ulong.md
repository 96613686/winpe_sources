# BinXmlReader::NextValueData(UserBuffer &,BinXmlVariant &,ulong)

- ea: `0x180004e70`
- end: `0x1800058ec`
- name: `?NextValueData@BinXmlReader@@AEAAXAEAVUserBuffer@@AEAUBinXmlVariant@@K@Z`
- size: `2684`
- prototype: `void(BinXmlReader *__hidden this, struct UserBuffer *, struct BinXmlVariant *, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004070`
- `0x180004db0`
- `0x180013398`
- `0x1800243cc`

## callees

- `0x180004e70`
- `0x1800130b0`
- `0x180013650`
- `0x18001a6cc`
- `0x18001ab18`
- `0x1800219dc`
- `0x1800231d0`
- `0x180023548`
- `0x18002fe24`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18000571f`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18000571f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000513c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000513c`

## pseudocode

```c
void __fastcall BinXmlReader::NextValueData(
        BinXmlReader *this,
        struct UserBuffer *a2,
        struct BinXmlVariant *a3,
        unsigned int a4)
{
  unsigned int v5; // esi
  int v6; // edx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // r9d
  __int64 v11; // rdx
  unsigned int v12; // r8d
  int v13; // edx
  int v14; // r9d
  __int64 v15; // rdx
  unsigned int v16; // ecx
  unsigned int v17; // esi
  int v18; // edx
  int v19; // edx
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // edx
  int v23; // edx
  int v24; // r8d
  unsigned int v25; // r15d
  unsigned int v26; // edx
  size_t v27; // rax
  __int64 v28; // rdx
  int v29; // edx
  int v30; // edx
  __int64 v31; // rdx
  size_t v32; // rax
  unsigned int v33; // eax
  __int128 pExceptionObject; // [rsp+20h] [rbp-30h] BYREF
  __int64 v35; // [rsp+30h] [rbp-20h]
  int v36; // [rsp+38h] [rbp-18h]
  int v37; // [rsp+3Ch] [rbp-14h]
  int v38; // [rsp+40h] [rbp-10h]

  v5 = a4;
  v6 = *((_DWORD *)a3 + 3);
  if ( (v6 & 0x80u) != 0 )
  {
    if ( a4 == -1 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
      }
      v35 = 0;
      v36 = 13;
      v37 = -1;
      pExceptionObject = 0;
      v38 = 959;
      throw (EvtException *)&pExceptionObject;
    }
    *(_QWORD *)a3 = *(_QWORD *)a2 + *((unsigned int *)a2 + 2);
    if ( !*(_QWORD *)a2 )
      goto LABEL_46;
    if ( a4 > 0x10000000 )
      goto LABEL_46;
    v24 = *((_DWORD *)a2 + 2);
    if ( a4 > *((_DWORD *)a2 + 3) - v24 )
      goto LABEL_46;
    v25 = 0;
    v26 = v6 & 0xFFFFFF7F;
    *((_DWORD *)a2 + 2) = v24 + a4;
    if ( v26 == 35 )
    {
LABEL_36:
      *((_DWORD *)a3 + 2) = 0;
      while ( v25 < v5 )
      {
        v27 = wcsnlen((const wchar_t *)(*(_QWORD *)a3 + v25), (unsigned __int64)(v5 - v25) >> 1);
        if ( v27 == (unsigned __int64)(v5 - v25) >> 1 || v27 >= 0x7FFFFFFF )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
          }
          v35 = 0;
          v36 = 13;
          v37 = -1;
          pExceptionObject = 0;
          v38 = 1058;
          throw (EvtException *)&pExceptionObject;
        }
        v25 += 2 * v27 + 2;
        ++*((_DWORD *)a3 + 2);
      }
    }
    else
    {
      if ( v26 != 4 )
      {
        switch ( v26 )
        {
          case 1u:
            goto LABEL_36;
          case 2u:
            *((_DWORD *)a3 + 2) = 0;
            while ( v25 < v5 )
            {
              v32 = strnlen((const char *)(*(_QWORD *)a3 + v25), v5 - v25);
              if ( v32 == v5 - v25 || v32 >= 0xFFFFFFFF )
              {
                if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids,
                    13);
                }
                v35 = 0;
                v36 = 13;
                v37 = -1;
                pExceptionObject = 0;
                v38 = 1076;
                throw (EvtException *)&pExceptionObject;
              }
              v25 += v32 + 1;
              ++*((_DWORD *)a3 + 2);
            }
            return;
          case 3u:
            break;
          case 5u:
          case 6u:
            if ( (a4 & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              pExceptionObject = 0;
              v38 = 977;
              throw (EvtException *)&pExceptionObject;
            }
            v5 = a4 >> 1;
            break;
          case 7u:
          case 8u:
          case 0xBu:
          case 0xDu:
          case 0x14u:
            if ( (a4 & 3) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              pExceptionObject = 0;
              v38 = 990;
              throw (EvtException *)&pExceptionObject;
            }
            v5 = a4 >> 2;
            break;
          case 9u:
          case 0xAu:
          case 0xCu:
          case 0x11u:
          case 0x15u:
            if ( (a4 & 7) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              pExceptionObject = 0;
              v38 = 1003;
              throw (EvtException *)&pExceptionObject;
            }
            goto LABEL_110;
          case 0xFu:
          case 0x12u:
            if ( (a4 & 0xF) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              pExceptionObject = 0;
              v38 = 1041;
              throw (EvtException *)&pExceptionObject;
            }
            v5 = a4 >> 4;
            break;
          case 0x10u:
            if ( (a4 & 3) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              pExceptionObject = 0;
              v38 = 1012;
              throw (EvtException *)&pExceptionObject;
            }
            *((_DWORD *)a3 + 3) = 148;
            *((_DWORD *)a3 + 2) = a4 >> 2;
            if ( (a4 & 7) != 0 )
              return;
            *((_DWORD *)a3 + 3) = 149;
LABEL_110:
            v5 = a4 >> 3;
            break;
          case 0x13u:
            *((_DWORD *)a3 + 2) = 0;
            if ( a4 )
            {
              do
              {
                v33 = SafeUnalignedSidLength((const unsigned __int8 *)(*(_QWORD *)a3 + v25), v5 - v25);
                ++*((_DWORD *)a3 + 2);
                v25 += v33;
              }
              while ( v25 < v5 );
            }
            return;
          default:
LABEL_58:
            *((_DWORD *)a3 + 2) = a4;
            ReadNLPString(a2, a4, a3);
            *((_DWORD *)a3 + 3) = 14;
            return;
        }
      }
      *((_DWORD *)a3 + 2) = v5;
    }
  }
  else
  {
    *((_DWORD *)a3 + 2) = 0;
    if ( v6 == 13 )
    {
LABEL_9:
      v15 = *((unsigned int *)a2 + 2);
      if ( (unsigned int)(*((_DWORD *)a2 + 3) - v15) < 4 )
        goto LABEL_46;
      *(_DWORD *)a3 = *(_DWORD *)(v15 + *(_QWORD *)a2);
      *((_DWORD *)a2 + 2) += 4;
    }
    else if ( v6 == 35 )
    {
LABEL_4:
      if ( a4 == -1 )
      {
        v8 = *((unsigned int *)a2 + 2);
        if ( (unsigned int)(*((_DWORD *)a2 + 3) - v8) >= 2 )
        {
          v9 = v8 + 2;
          v10 = *(unsigned __int16 *)(v8 + *(_QWORD *)a2);
          v11 = *(_QWORD *)a2 + (unsigned int)(v8 + 2);
          *((_DWORD *)a2 + 2) = v9;
          *(_QWORD *)a3 = v11;
          if ( *(_QWORD *)a2 )
          {
            v12 = 2 * v10;
            v13 = v10;
            v14 = *((_DWORD *)a2 + 2);
            if ( v12 <= *((_DWORD *)a2 + 3) - v14 )
            {
              *((_DWORD *)a2 + 2) = v12 + v14;
              *((_DWORD *)a3 + 2) = v13;
              return;
            }
          }
        }
LABEL_46:
        UserBuffer::ThrowUnexpectedEOFException();
      }
      *((_DWORD *)a3 + 2) = a4 >> 1;
      *(_QWORD *)a3 = *(_QWORD *)a2 + *((unsigned int *)a2 + 2);
      if ( !*(_QWORD *)a2 )
        goto LABEL_46;
      v17 = 2 * (a4 >> 1);
      if ( v17 > 0x10000000 )
        goto LABEL_46;
      v18 = *((_DWORD *)a2 + 2);
      if ( v17 > *((_DWORD *)a2 + 3) - v18 )
        goto LABEL_46;
      *((_DWORD *)a2 + 2) = v17 + v18;
      v19 = *((_DWORD *)a3 + 2);
      if ( v19 )
      {
        v20 = (unsigned int)(v19 - 1);
        if ( !*(_WORD *)(*(_QWORD *)a3 + 2 * v20) )
          *((_DWORD *)a3 + 2) = v20;
      }
    }
    else
    {
      switch ( v6 )
      {
        case 0:
          if ( a4 != -1 )
            UserBuffer::Advance(a2, a4);
          return;
        case 1:
          goto LABEL_4;
        case 2:
          if ( a4 == -1 )
            goto LABEL_67;
          *((_DWORD *)a3 + 2) = a4;
          *(_QWORD *)a3 = *(_QWORD *)a2 + *((unsigned int *)a2 + 2);
          if ( !*(_QWORD *)a2 )
            goto LABEL_46;
          if ( a4 > 0x10000000 )
            goto LABEL_46;
          v29 = *((_DWORD *)a2 + 2);
          if ( a4 > *((_DWORD *)a2 + 3) - v29 )
            goto LABEL_46;
          *((_DWORD *)a2 + 2) = v29 + a4;
          v30 = *((_DWORD *)a3 + 2);
          if ( v30 )
          {
            v31 = (unsigned int)(v30 - 1);
            if ( !*(_BYTE *)(v31 + *(_QWORD *)a3) )
              *((_DWORD *)a3 + 2) = v31;
          }
          return;
        case 3:
        case 4:
          v16 = *((_DWORD *)a2 + 2);
          if ( v16 >= *((_DWORD *)a2 + 3) )
            goto LABEL_46;
          *(_BYTE *)a3 = *(_BYTE *)(v16 + *(_QWORD *)a2);
          ++*((_DWORD *)a2 + 2);
          return;
        case 5:
        case 6:
          v21 = *((unsigned int *)a2 + 2);
          if ( (unsigned int)(*((_DWORD *)a2 + 3) - v21) < 2 )
            goto LABEL_46;
          *(_WORD *)a3 = *(_WORD *)(v21 + *(_QWORD *)a2);
          *((_DWORD *)a2 + 2) += 2;
          return;
        case 7:
        case 8:
        case 11:
        case 20:
          goto LABEL_9;
        case 9:
        case 10:
        case 12:
        case 17:
        case 21:
          v28 = *((unsigned int *)a2 + 2);
          if ( (unsigned int)(*((_DWORD *)a2 + 3) - v28) < 8 )
            goto LABEL_46;
          *(_QWORD *)a3 = *(_QWORD *)(v28 + *(_QWORD *)a2);
          *((_DWORD *)a2 + 2) += 8;
          return;
        case 14:
        case 19:
          if ( a4 == -1 )
          {
LABEL_67:
            ReadLPString_0(a2, (char *)a3 + 8, a3);
          }
          else
          {
            *((_DWORD *)a3 + 2) = a4;
            *(_QWORD *)a3 = *(_QWORD *)a2 + *((unsigned int *)a2 + 2);
            if ( !*(_QWORD *)a2 )
              goto LABEL_46;
            if ( a4 > 0x10000000 )
              goto LABEL_46;
            v22 = *((_DWORD *)a2 + 2);
            if ( a4 > *((_DWORD *)a2 + 3) - v22 )
              goto LABEL_46;
            *((_DWORD *)a2 + 2) = v22 + a4;
          }
          break;
        case 15:
        case 18:
          *(_QWORD *)a3 = *(_QWORD *)a2 + *((unsigned int *)a2 + 2);
          if ( !*(_QWORD *)a2 )
            goto LABEL_46;
          v23 = *((_DWORD *)a2 + 2);
          if ( (unsigned int)(*((_DWORD *)a2 + 3) - v23) < 0x10 )
            goto LABEL_46;
          *((_DWORD *)a2 + 2) = v23 + 16;
          return;
        case 16:
          if ( a4 == 4 )
          {
            *((_DWORD *)a3 + 3) = 20;
            UserBuffer::Read4(a2, a3);
          }
          else
          {
            if ( a4 != 8 )
            {
              if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
              }
              v35 = 0;
              v36 = 13;
              v37 = -1;
              v38 = 861;
              pExceptionObject = 0;
              throw (EvtException *)&pExceptionObject;
            }
            *((_DWORD *)a3 + 3) = 21;
            UserBuffer::Read8(a2, a3);
          }
          return;
        default:
          if ( a4 == -1 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
            }
            v35 = 0;
            v36 = 13;
            v37 = -1;
            pExceptionObject = 0;
            v38 = 942;
            throw (EvtException *)&pExceptionObject;
          }
          goto LABEL_58;
      }
    }
  }
}

```

## disassembly

```asm
0x180004e70  mov     [rsp-18h+arg_10], rsi
0x180004e75  push    rbp
0x180004e76  push    rdi
0x180004e77  push    r14
0x180004e79  mov     rbp, rsp
0x180004e7c  sub     rsp, 50h
0x180004e80  mov     rax, rdx
0x180004e83  mov     esi, r9d
0x180004e86  mov     edx, [r8+0Ch]
0x180004e8a  mov     rdi, r8
0x180004e8d  test    dl, dl
0x180004e8f  js      loc_1800050C5
0x180004e95  mov     dword ptr [r8+8], 0
0x180004e9d  cmp     edx, 0Dh
0x180004ea0  jz      short loc_180004F20; jumptable 0000000180004F69 cases 7,8,11,20
0x180004ea2  cmp     edx, 23h ; '#'
0x180004ea5  jnz     loc_180004F4E
0x180004eab  mov     r14d, 0FFFFFFFFh; jumptable 0000000180004F69 case 1
0x180004eb1  cmp     esi, r14d
0x180004eb4  jnz     loc_180004F96
0x180004eba  mov     edx, [rax+8]
0x180004ebd  mov     ecx, [rax+0Ch]
0x180004ec0  sub     ecx, edx
0x180004ec2  cmp     ecx, 2
0x180004ec5  jb      loc_1800051AB
0x180004ecb  mov     r8, [rax]
0x180004ece  lea     ecx, [rdx+2]
0x180004ed1  movzx   r9d, word ptr [rdx+r8]
0x180004ed6  mov     edx, ecx
0x180004ed8  add     rdx, r8
0x180004edb  mov     [rax+8], ecx
0x180004ede  mov     [rdi], rdx
0x180004ee1  cmp     qword ptr [rax], 0
0x180004ee5  jz      loc_1800051AB
0x180004eeb  mov     ecx, [rax+0Ch]
0x180004eee  lea     r8d, [r9+r9]
0x180004ef2  mov     edx, r9d
0x180004ef5  mov     r9d, [rax+8]
0x180004ef9  sub     ecx, r9d
0x180004efc  cmp     r8d, ecx
0x180004eff  ja      loc_1800051AB
0x180004f05  lea     ecx, [r8+r9]
0x180004f09  mov     [rax+8], ecx
0x180004f0c  mov     [rdi+8], edx
0x180004f0f  mov     rsi, [rsp+50h+arg_10]
0x180004f17  add     rsp, 50h
0x180004f1b  pop     r14
0x180004f1d  pop     rdi
0x180004f1e  pop     rbp
0x180004f1f  retn
0x180004f20  mov     edx, [rax+8]; jumptable 0000000180004F69 cases 7,8,11,20
0x180004f23  mov     ecx, [rax+0Ch]
0x180004f26  sub     ecx, edx
0x180004f28  cmp     ecx, 4
0x180004f2b  jb      loc_1800051AB
0x180004f31  mov     rcx, [rax]
0x180004f34  mov     edx, [rdx+rcx]
0x180004f37  mov     [rdi], edx
0x180004f39  add     dword ptr [rax+8], 4
0x180004f3d  mov     rsi, [rsp+50h+arg_10]
0x180004f45  add     rsp, 50h
0x180004f49  pop     r14
0x180004f4b  pop     rdi
0x180004f4c  pop     rbp
0x180004f4d  retn
0x180004f4e  cmp     edx, 15h; switch 22 cases
0x180004f51  ja      def_180004F69; jumptable 0000000180004F69 default case, case 13
0x180004f57  lea     r8, __ImageBase
0x180004f5e  mov     ecx, ds:(jpt_180004F69 - 180000000h)[r8+rdx*4]
0x180004f66  add     rcx, r8
0x180004f69  jmp     rcx; switch jump
0x180004f6b  mov     ecx, [rax+8]; jumptable 0000000180004F69 cases 3,4
0x180004f6e  cmp     ecx, [rax+0Ch]
0x180004f71  jnb     loc_1800051AB
0x180004f77  mov     edx, ecx
0x180004f79  mov     rcx, [rax]
0x180004f7c  movzx   edx, byte ptr [rdx+rcx]
0x180004f80  mov     [rdi], dl
0x180004f82  inc     dword ptr [rax+8]
0x180004f85  mov     rsi, [rsp+50h+arg_10]
0x180004f8d  add     rsp, 50h
0x180004f91  pop     r14
0x180004f93  pop     rdi
0x180004f94  pop     rbp
0x180004f95  retn
0x180004f96  shr     esi, 1
0x180004f98  mov     [rdi+8], esi
0x180004f9b  mov     ecx, [rax+8]
0x180004f9e  add     rcx, [rax]
0x180004fa1  mov     [rdi], rcx
0x180004fa4  cmp     qword ptr [rax], 0
0x180004fa8  jz      loc_1800051AB
0x180004fae  add     esi, esi
0x180004fb0  cmp     esi, 10000000h
0x180004fb6  ja      loc_1800051AB
0x180004fbc  mov     ecx, [rax+0Ch]
0x180004fbf  mov     edx, [rax+8]
0x180004fc2  sub     ecx, edx
0x180004fc4  cmp     esi, ecx
0x180004fc6  ja      loc_1800051AB
0x180004fcc  lea     ecx, [rsi+rdx]
0x180004fcf  mov     [rax+8], ecx
0x180004fd2  mov     edx, [rdi+8]
0x180004fd5  test    edx, edx
0x180004fd7  jz      loc_180004F3D
0x180004fdd  mov     rax, [rdi]
0x180004fe0  dec     edx
0x180004fe2  cmp     word ptr [rax+rdx*2], 0
0x180004fe7  jnz     loc_180004F3D
0x180004fed  mov     [rdi+8], edx
0x180004ff0  mov     rsi, [rsp+50h+arg_10]
0x180004ff8  add     rsp, 50h
0x180004ffc  pop     r14
0x180004ffe  pop     rdi
0x180004fff  pop     rbp
0x180005000  retn
0x180005001  mov     edx, [rax+8]; jumptable 0000000180004F69 cases 5,6
0x180005004  mov     ecx, [rax+0Ch]
0x180005007  sub     ecx, edx
0x180005009  cmp     ecx, 2
0x18000500c  jb      loc_1800051AB
0x180005012  mov     rcx, [rax]
0x180005015  movzx   edx, word ptr [rdx+rcx]
0x180005019  mov     [rdi], dx
0x18000501c  add     dword ptr [rax+8], 2
0x180005020  mov     rsi, [rsp+50h+arg_10]
0x180005028  add     rsp, 50h
0x18000502c  pop     r14
0x18000502e  pop     rdi
0x18000502f  pop     rbp
0x180005030  retn
0x180005031  mov     r14d, 0FFFFFFFFh; jumptable 0000000180004F69 cases 14,19
0x180005037  cmp     esi, r14d
0x18000503a  jz      loc_18000535D
0x180005040  mov     [rdi+8], esi
0x180005043  mov     ecx, [rax+8]
0x180005046  add     rcx, [rax]
0x180005049  mov     [rdi], rcx
0x18000504c  cmp     qword ptr [rax], 0
0x180005050  jz      loc_1800051AB
0x180005056  cmp     esi, 10000000h
0x18000505c  ja      loc_1800051AB
0x180005062  mov     ecx, [rax+0Ch]
0x180005065  mov     edx, [rax+8]
0x180005068  sub     ecx, edx
0x18000506a  cmp     esi, ecx
0x18000506c  ja      loc_1800051AB
0x180005072  lea     ecx, [rdx+r9]
0x180005076  mov     [rax+8], ecx
0x180005079  mov     rsi, [rsp+50h+arg_10]
0x180005081  add     rsp, 50h
0x180005085  pop     r14
0x180005087  pop     rdi
0x180005088  pop     rbp
0x180005089  retn
0x18000508a  mov     ecx, [rax+8]; jumptable 0000000180004F69 cases 15,18
0x18000508d  add     rcx, [rax]
0x180005090  mov     [rdi], rcx
0x180005093  cmp     qword ptr [rax], 0
0x180005097  jz      loc_1800051AB
0x18000509d  mov     ecx, [rax+0Ch]
0x1800050a0  mov     edx, [rax+8]
0x1800050a3  sub     ecx, edx
0x1800050a5  cmp     ecx, 10h
0x1800050a8  jb      loc_1800051AB
0x1800050ae  lea     ecx, [rdx+10h]
0x1800050b1  mov     [rax+8], ecx
0x1800050b4  mov     rsi, [rsp+50h+arg_10]
0x1800050bc  add     rsp, 50h
0x1800050c0  pop     r14
0x1800050c2  pop     rdi
0x1800050c3  pop     rbp
0x1800050c4  retn
0x1800050c5  mov     r14d, 0FFFFFFFFh
0x1800050cb  cmp     esi, r14d
0x1800050ce  jz      loc_180005410
0x1800050d4  mov     ecx, [rax+8]
0x1800050d7  add     rcx, [rax]
0x1800050da  mov     [r8], rcx
0x1800050dd  cmp     qword ptr [rax], 0
0x1800050e1  jz      loc_1800051AB
0x1800050e7  cmp     esi, 10000000h
0x1800050ed  ja      loc_1800051AB
0x1800050f3  mov     ecx, [rax+0Ch]
0x1800050f6  mov     r8d, [rax+8]
0x1800050fa  sub     ecx, r8d
0x1800050fd  cmp     esi, ecx
0x1800050ff  ja      loc_1800051AB
0x180005105  mov     [rsp+50h+arg_8], r15
0x18000510a  lea     ecx, [r8+r9]
0x18000510e  xor     r15d, r15d
0x180005111  mov     [rsp+50h+arg_0], rbx
0x180005116  btr     edx, 7
0x18000511a  mov     [rax+8], ecx
0x18000511d  cmp     edx, 23h ; '#'
0x180005120  jnz     short loc_180005164
0x180005122  mov     [rdi+8], r15d; jumptable 000000018000548F case 1
0x180005126  cmp     r15d, esi
0x180005129  jnb     short loc_180005170
0x18000512b  mov     ebx, esi
0x18000512d  mov     ecx, r15d
0x180005130  add     rcx, [rdi]; Source
0x180005133  sub     ebx, r15d
0x180005136  shr     rbx, 1
0x180005139  mov     rdx, rbx; MaxCount
0x18000513c  call    cs:__imp_wcsnlen
0x180005142  cmp     rax, rbx
0x180005145  jz      loc_1800057D3
0x18000514b  cmp     rax, 7FFFFFFFh
0x180005151  jnb     loc_1800057D3
0x180005157  lea     r15d, [r15+rax*2]
0x18000515b  add     r15d, 2
0x18000515f  inc     dword ptr [rdi+8]
0x180005162  jmp     short loc_180005126
0x180005164  cmp     edx, 4
0x180005167  jnz     loc_18000524F
0x18000516d  mov     [rdi+8], esi; jumptable 000000018000548F case 3
0x180005170  mov     rbx, [rsp+50h+arg_0]
0x180005175  mov     r15, [rsp+50h+arg_8]
0x18000517a  jmp     loc_180004F3D
0x18000517f  mov     edx, [rax+8]; jumptable 0000000180004F69 cases 9,10,12,17,21
0x180005182  mov     ecx, [rax+0Ch]
0x180005185  sub     ecx, edx
0x180005187  cmp     ecx, 8
0x18000518a  jb      short loc_1800051AB
0x18000518c  mov     rcx, [rax]
0x18000518f  mov     rdx, [rdx+rcx]
0x180005193  mov     [rdi], rdx
0x180005196  add     dword ptr [rax+8], 8
0x18000519a  mov     rsi, [rsp+50h+arg_10]
0x1800051a2  add     rsp, 50h
0x1800051a6  pop     r14
0x1800051a8  pop     rdi
0x1800051a9  pop     rbp
0x1800051aa  retn
0x1800051ab  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x1800051b1  mov     r14d, 0FFFFFFFFh; jumptable 0000000180004F69 case 2
0x1800051b7  cmp     esi, r14d
0x1800051ba  jz      loc_18000533E
0x1800051c0  mov     [rdi+8], esi
0x1800051c3  mov     ecx, [rax+8]
0x1800051c6  add     rcx, [rax]
0x1800051c9  mov     [rdi], rcx
0x1800051cc  cmp     qword ptr [rax], 0
0x1800051d0  jz      short loc_1800051AB
0x1800051d2  cmp     esi, 10000000h
0x1800051d8  ja      short loc_1800051AB
0x1800051da  mov     ecx, [rax+0Ch]
0x1800051dd  mov     edx, [rax+8]
0x1800051e0  sub     ecx, edx
0x1800051e2  cmp     esi, ecx
0x1800051e4  ja      short loc_1800051AB
0x1800051e6  lea     ecx, [rdx+r9]
0x1800051ea  mov     [rax+8], ecx
0x1800051ed  mov     edx, [rdi+8]
0x1800051f0  test    edx, edx
0x1800051f2  jz      loc_180004F3D
0x1800051f8  mov     rax, [rdi]
0x1800051fb  dec     edx
0x1800051fd  cmp     byte ptr [rdx+rax], 0
0x180005201  jnz     loc_180004F3D
0x180005207  mov     [rdi+8], edx
0x18000520a  mov     rsi, [rsp+50h+arg_10]
0x180005212  add     rsp, 50h
0x180005216  pop     r14
0x180005218  pop     rdi
0x180005219  pop     rbp
0x18000521a  retn
0x18000521b  cmp     esi, 4; jumptable 0000000180004F69 case 16
0x18000521e  jz      loc_1800052A9
0x180005224  cmp     esi, 8
0x180005227  jnz     loc_1800052CB
0x18000522d  mov     rdx, rdi; void *
0x180005230  mov     dword ptr [rdi+0Ch], 15h
0x180005237  mov     rcx, rax; this
0x18000523a  mov     rsi, [rsp+50h+arg_10]
0x180005242  add     rsp, 50h
0x180005246  pop     r14
0x180005248  pop     rdi
0x180005249  pop     rbp
0x18000524a  jmp     ?Read8@UserBuffer@@QEAAXPEAX@Z; UserBuffer::Read8(void *)
0x18000524f  dec     edx; switch 21 cases
0x180005251  cmp     edx, 14h
0x180005254  jbe     loc_18000547D
0x18000525a  mov     r8, rdi; jumptable 000000018000548F default case, cases 4,14
0x18000525d  mov     [rdi+8], esi
0x180005260  mov     edx, esi
0x180005262  mov     rcx, rax
0x180005265  call    ReadNLPString
0x18000526a  mov     rbx, [rsp+50h+arg_0]
0x18000526f  mov     r15, [rsp+50h+arg_8]
0x180005274  mov     dword ptr [rdi+0Ch], 0Eh
0x18000527b  jmp     loc_180004F3D
0x180005280  mov     r14d, 0FFFFFFFFh; jumptable 0000000180004F69 case 0
0x180005286  cmp     esi, r14d
0x180005289  jz      loc_180004F3D
0x18000528f  mov     edx, esi; unsigned int
0x180005291  mov     rcx, rax; this
0x180005294  mov     rsi, [rsp+50h+arg_10]
0x18000529c  add     rsp, 50h
  ... truncated ...
```
