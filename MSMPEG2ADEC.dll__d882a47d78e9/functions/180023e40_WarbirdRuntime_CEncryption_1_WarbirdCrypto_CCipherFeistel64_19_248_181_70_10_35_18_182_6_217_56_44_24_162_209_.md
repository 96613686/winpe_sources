# WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *)

- ea: `0x180023e40`
- end: `0x180023ec1`
- name: `?Encrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@@Z`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b900`
- `0x18001e410`

## callees

- `0x180022470`
- `0x180023e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ea8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ea8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e61`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Encrypt()
{
  __int64 v1; // rdx
  unsigned int v2; // ebx

  if ( !WarbirdRuntime::g_EncryptedSegmentConstData_4 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 == 1 )
  {
    v2 = WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(
           1,
           v1,
           1);
    WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 = 0;
  }
  else
  {
    v2 = 0;
    if ( (unsigned int)(WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 - 1) <= 0xFFFFFFFD )
      --WarbirdRuntime::g_EncryptedSegmentReadWriteData_4;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return v2;
}

```

## disassembly

```asm
0x180023e40  sub     rsp, 28h
0x180023e44  test    byte ptr cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_EncryptedSegmentConstData_4
0x180023e4b  jnz     short loc_180023E55
0x180023e4d  xor     eax, eax
0x180023e4f  add     rsp, 28h
0x180023e53  retn
0x180023e55  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180023e5c  mov     [rsp+28h+var_8], rbx
0x180023e61  call    cs:__imp_EnterCriticalSection
0x180023e68  nop     dword ptr [rax+rax+00h]
0x180023e6d  mov     ecx, cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x180023e73  cmp     ecx, 1
0x180023e76  jnz     short loc_180023E8E
0x180023e78  mov     r8d, ecx
0x180023e7b  call    ?DoCrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@H@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *,int)
0x180023e80  mov     ebx, eax
0x180023e82  mov     cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A, 0; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x180023e8c  jmp     short loc_180023EA1
0x180023e8e  xor     ebx, ebx
0x180023e90  lea     eax, [rcx-1]
0x180023e93  cmp     eax, 0FFFFFFFDh
0x180023e96  ja      short loc_180023EA1
0x180023e98  lea     eax, [rcx-1]
0x180023e9b  mov     cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x180023ea1  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180023ea8  call    cs:__imp_LeaveCriticalSection
0x180023eaf  nop     dword ptr [rax+rax+00h]
0x180023eb4  mov     eax, ebx
0x180023eb6  mov     rbx, [rsp+28h+var_8]
0x180023ebb  add     rsp, 28h
0x180023ebf  retn
```
