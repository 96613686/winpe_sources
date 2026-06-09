# TextizeJetErrorHresult(long)

- ea: `0x140018c50`
- end: `0x14001a08d`
- name: `?TextizeJetErrorHresult@@YAPEBDJ@Z`
- size: `5181`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001272c`

## callees

- `0x140018c50`

## string_xrefs

- `0x140018d0c`: `JET_errOutOfThreads`
- `0x140018d56`: `JET_errTaskDropped`
- `0x140018dbb`: `JET_errBadPageLink`
- `0x140018d99`: `JET_errBadParentPageLink`
- `0x140018dcb`: `JET_errSPAvailExtCacheOutOfSync`
- `0x140018e05`: `JET_errSPAvailExtCacheOutOfMemory`
- `0x140018e6d`: `JET_errNoBackupDirectory`
- `0x140018e5b`: `JET_errBackupDirectoryNotEmpty`
- `0x140018ecf`: `JET_errLogWriteFail`
- `0x140018eb5`: `JET_errCannotLogDuringRecoveryRedo`
- `0x140018f54`: `JET_errDeleteBackupFileFail`
- `0x140018f5c`: `JET_errMakeBackupDirectoryFail`
- `0x140019091`: `JET_errDatabaseAlreadyUpgraded`
- `0x140019099`: `JET_errDatabaseIncompleteUpgrade`
- `0x1400190c1`: `JET_errLogTornWriteDuringHardRestore`
- `0x1400190c9`: `JET_errLogTornWriteDuringHardRecovery`
- `0x1400190d1`: `JET_errLogCorruptDuringHardRestore`
- `0x1400190d9`: `JET_errLogCorruptDuringHardRecovery`
- `0x140019187`: `JET_errCommittedLogFilesMissing`
- `0x140019ee8`: `JET_wrnCommittedLogFilesLost`
- `0x140019165`: `JET_errCommittedLogFileCorrupt`
- `0x140019ee0`: `JET_wrnCommittedLogFilesRemoved`
- `0x140019ed8`: `JET_wrnDatabaseRepaired`
- `0x1400191bf`: `JET_errLogReadVerifyFailure`
- `0x140019290`: `JET_errDatabaseFileReadOnly`
- `0x1400192e5`: `JET_errRecordDeleted`
- `0x1400192ed`: `JET_errReadVerifyFailure`
- `0x14001930d`: `JET_errInvalidPath`
- `0x140019315`: `JET_errInvalidSystemPath`
- `0x14001931d`: `JET_errInvalidLogDirectory`
- `0x14001932d`: `JET_errTooManyOpenDatabases`
- `0x140019345`: `JET_errAlreadyInitialized`
- `0x140019355`: `JET_errFileAccessDenied`
- `0x14001936d`: `JET_errContainerNotEmpty`
- `0x1400193d2`: `JET_errLinkNotSupported`
- `0x140019fa4`: `JET_wrnNoWriteLock`
- `0x140019432`: `JET_errRecordNotDeleted`
- `0x14001947a`: `JET_errSystemParamsAlreadySet`
- `0x140019482`: `JET_errSystemPathInUse`
- `0x14001948a`: `JET_errLogFilePathInUse`
- `0x140019492`: `JET_errTempPathInUse`
- `0x1400194c2`: `JET_errWriteConflict`
- `0x1400194d2`: `JET_errInvalidSesid`
- `0x1400194da`: `JET_errWriteConflictPrimaryIndex`
- `0x1400194ea`: `JET_errRollbackRequired`
- `0x1400194f2`: `JET_errTransReadOnly`
- `0x1400194fa`: `JET_errSessionWriteConflict`
- `0x140019502`: `JET_errRecordTooBigForBackwardCompatibility`
- `0x140019512`: `JET_errSesidTableIdMismatch`
- `0x14001967a`: `JET_errDatabaseInvalidPath`
- `0x140019712`: `JET_errDatabaseCorruptedNoRepair`
- `0x14001970a`: `JET_errInvalidCreateDbVersion`
- `0x140019764`: `JET_errTableNotEmpty`
- `0x140019754`: `JET_errTooManyOpenTables`
- `0x140019774`: `JET_errTooManyOpenTablesAndCleanupTimedOut`
- `0x1400197c1`: `JET_errCannotDeleteTempTable`
- `0x1400197b9`: `JET_errCannotDeleteSystemTable`
- `0x1400197a7`: `JET_errCannotDeleteTemplateTable`
- `0x1400198a6`: `JET_errClientRequestToStopJetService`
- `0x1400198f0`: `JET_errInvalidCreateIndex`
- `0x1400198e8`: `JET_errTooManyOpenIndexes`
- `0x140019f84`: `JET_wrnCorruptIndexDeleted`
- `0x140019fe7`: `JET_wrnCopyLongValue`
- `0x140019b1a`: `JET_errRecordNoCopy`
- `0x140019b84`: `JET_errAlreadyPrepared`
- `0x140019b74`: `JET_errUpdateNotPrepared`
- `0x140019be1`: `JET_errTempFileOpenError`
- `0x14001a046`: `JET_wrnFileOpenReadOnly`
- `0x140019c3b`: `JET_errAccessDenied`
- `0x140019c93`: `JET_errSessionContextAlreadySet`
- `0x140019c81`: `JET_errSessionContextNotSetByThisThread`
- `0x140019cf5`: `JET_errRollbackError`
- `0x14001a07d`: `JET_wrnDefragAlreadyRunning`
- `0x140019d72`: `JET_errLSAlreadySet`
- `0x140019e37`: `JET_errFileCompressed`

## pseudocode

```c
const char *__fastcall TextizeJetErrorHresult(int a1)
{
  const char *v1; // rdx
  bool v2; // zf
  const char *result; // rax
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx

  if ( a1 > -1906441125 )
  {
    if ( a1 > -1906440711 )
    {
      if ( a1 > -1906438237 )
      {
        if ( a1 > 241042466 )
        {
          if ( a1 > 241042942 )
          {
            if ( a1 > 241043221 )
            {
              v26 = a1 - 241043316;
              if ( !v26 )
                return "JET_wrnIdleFull";
              v27 = v26 - 92;
              if ( !v27 )
                return "JET_wrnDefragAlreadyRunning";
              v28 = v27 - 1;
              if ( !v28 )
                return "JET_wrnDefragNotRunning";
              if ( v28 == 99 )
                return "JET_wrnCallbackNotRegistered";
            }
            else
            {
              if ( a1 == 241043221 )
                return "JET_wrnFileOpenReadOnly";
              v22 = a1 - 241042943;
              if ( !v22 )
                return "JET_wrnColumnPresent";
              v23 = v22 - 1;
              if ( !v23 )
                return "JET_wrnColumnSingleValue";
              v24 = v23 - 1;
              if ( !v24 )
                return "JET_wrnColumnDefault";
              v25 = v24 - 73;
              if ( !v25 )
                return "JET_wrnDataHasChanged";
              if ( v25 == 8 )
                return "JET_wrnKeyChanged";
            }
          }
          else
          {
            if ( a1 == 241042942 )
              return "JET_wrnColumnTruncated";
            if ( a1 > 241042920 )
            {
              v19 = a1 - 241042928;
              if ( !v19 )
                return "JET_wrnCopyLongValue";
              v20 = v19 - 11;
              if ( !v20 )
                return "JET_wrnColumnSkipped";
              v21 = v20 - 1;
              if ( !v21 )
                return "JET_wrnColumnNotLocal";
              if ( v21 == 1 )
                return "JET_wrnColumnMoreTags";
            }
            else
            {
              if ( a1 == 241042920 )
                return "JET_wrnColumnMaxTruncated";
              v15 = a1 - 241042475;
              if ( !v15 )
                return "JET_wrnNoWriteLock";
              v16 = v15 - 1;
              if ( !v16 )
                return "JET_wrnColumnSetNull";
              v17 = v16 - 233;
              if ( !v17 )
                return "JET_wrnTableEmpty";
              v18 = v17 - 26;
              if ( !v18 )
                return "JET_wrnTableInUseBySystem";
              if ( v18 == 88 )
                return "JET_wrnCorruptIndexDeleted";
            }
          }
        }
        else
        {
          if ( a1 == 241042466 )
            return "JET_wrnNoIdleActivity";
          if ( a1 > 241041972 )
          {
            if ( a1 > 241042414 )
            {
              v12 = a1 - 241042415;
              if ( !v12 )
                return "JET_wrnDatabaseAttached";
              v13 = v12 - 2;
              if ( !v13 )
                return "JET_wrnSortOverflow";
              v14 = v13 - 30;
              if ( !v14 )
                return "JET_wrnSeekNotEqual";
              if ( v14 == 16 )
                return "JET_wrnNoErrorInfo";
            }
            else
            {
              if ( a1 == 241042414 )
                return "JET_wrnBufferTruncated";
              v8 = a1 - 241041986;
              if ( !v8 )
                return "JET_wrnTargetInstanceRunning";
              v9 = v8 - 7;
              if ( !v9 )
                return "JET_wrnCommittedLogFilesLost";
              v10 = v9 - 2;
              if ( !v10 )
                return "JET_wrnCommittedLogFilesRemoved";
              v11 = v10 - 8;
              if ( !v11 )
                return "JET_wrnDatabaseRepaired";
              if ( v11 == 409 )
                return "JET_wrnColumnNull";
            }
          }
          else
          {
            if ( a1 == 241041972 )
              return "JET_wrnSkipThisRecord";
            if ( a1 <= 241041507 )
            {
              switch ( a1 )
              {
                case 241041507:
                  return "JET_errIndexTuplesTextColumnsOnly";
                case -1906438236:
                  return "JET_errFileIOFail";
                case -1906438235:
                  return "JET_errFileCompressed";
                case 0:
                  return "JET_errSuccess";
                case 241041489:
                  return "JET_errDatabaseInconsistent";
              }
              v1 = "JET_errIndexTuplesOneColumnOnly";
              v2 = a1 == 241041498;
              goto LABEL_514;
            }
            v4 = a1 - 241041729;
            if ( !v4 )
              return "JET_wrnRemainingVersions";
            v5 = v4 - 24;
            if ( !v5 )
              return "JET_wrnUniqueKey";
            v6 = v5 - 61;
            if ( !v6 )
              return "JET_wrnSeparateLongValue";
            v7 = v6 - 152;
            if ( !v7 )
              return "JET_wrnExistingLogFileHasBadSignature";
            if ( v7 == 1 )
              return "JET_wrnExistingLogFileIsNotContiguous";
          }
        }
        return "Unknown Error";
      }
      if ( a1 == -1906438237 )
        return "JET_errFileIORetry";
      if ( a1 > -1906440333 )
      {
        if ( a1 > -1906440137 )
        {
          if ( a1 > -1906439239 )
          {
            switch ( a1 )
            {
              case -1906439238:
                return "JET_errLSNotSet";
              case -1906438240:
                return "JET_errFileIOSparse";
              case -1906438239:
                return "JET_errFileIOBeyondEOF";
            }
            v1 = "JET_errFileIOAbort";
            v2 = a1 == -1906438238;
          }
          else
          {
            switch ( a1 )
            {
              case -1906439239:
                return "JET_errLSAlreadySet";
              case -1906439839:
                return "JET_errOSSnapshotInvalidSequence";
              case -1906439838:
                return "JET_errOSSnapshotTimeOut";
              case -1906439837:
                return "JET_errOSSnapshotNotAllowed";
              case -1906439836:
                return "JET_errOSSnapshotInvalidSnapId";
            }
            v1 = "JET_errLSCallbackNotSpecified";
            v2 = a1 == -1906439240;
          }
        }
        else
        {
          if ( a1 == -1906440137 )
            return "JET_errSpaceHintsInvalid";
          if ( a1 > -1906440326 )
          {
            switch ( a1 )
            {
              case -1906440325:
                return "JET_errRecordFormatConversionFailed";
              case -1906440324:
                return "JET_errOneDatabasePerSession";
              case -1906440323:
                return "JET_errRollbackError";
              case -1906440139:
                return "JET_errCallbackFailed";
            }
            v1 = "JET_errCallbackNotResolved";
            v2 = a1 == -1906440138;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440326:
                return "JET_errSessionInUse";
              case -1906440331:
                return "JET_errTooManySplits";
              case -1906440330:
                return "JET_errSessionSharingViolation";
              case -1906440329:
                return "JET_errEntryPointNotFound";
              case -1906440328:
                return "JET_errSessionContextAlreadySet";
            }
            v1 = "JET_errSessionContextNotSetByThisThread";
            v2 = a1 == -1906440327;
          }
        }
      }
      else
      {
        if ( a1 == -1906440333 )
          return "JET_errAccessDenied";
        if ( a1 > -1906440539 )
        {
          if ( a1 > -1906440429 )
          {
            switch ( a1 )
            {
              case -1906440428:
                return "JET_errFileInvalidType";
              case -1906440390:
                return "JET_errAfterInitialization";
              case -1906440388:
                return "JET_errLogCorrupted";
            }
            v1 = "JET_errInvalidOperation";
            v2 = a1 == -1906440334;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440429:
                return "JET_errFileNotFound";
              case -1906440538:
                return "JET_errInvalidOnSort";
              case -1906440437:
                return "JET_errTempFileOpenError";
              case -1906440435:
                return "JET_errTooManyAttachedDatabases";
              case -1906440432:
                return "JET_errDiskFull";
            }
            v1 = "JET_errPermissionDenied";
            v2 = a1 == -1906440431;
          }
        }
        else
        {
          if ( a1 == -1906440539 )
            return "JET_errTooManySorts";
          if ( a1 > -1906440635 )
          {
            switch ( a1 )
            {
              case -1906440633:
                return "JET_errAlreadyPrepared";
              case -1906440632:
                return "JET_errKeyNotMade";
              case -1906440631:
                return "JET_errUpdateNotPrepared";
              case -1906440629:
                return "JET_errDataHasChanged";
            }
            v1 = "JET_errLanguageNotSupported";
            v2 = a1 == -1906440621;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440635:
                return "JET_errKeyDuplicate";
              case -1906440710:
                return "JET_errInvalidPlaceholderColumn";
              case -1906440639:
                return "JET_errRecordNotFound";
              case -1906440638:
                return "JET_errRecordNoCopy";
              case -1906440637:
                return "JET_errNoCurrentRecord";
            }
            v1 = "JET_errRecordPrimaryChanged";
            v2 = a1 == -1906440636;
          }
        }
      }
LABEL_514:
      result = "Unknown Error";
      if ( v2 )
        return v1;
      return result;
    }
    if ( a1 == -1906440711 )
      return "JET_errDerivedColumnCorruption";
    if ( a1 > -1906440912 )
    {
      if ( a1 <= -1906440803 )
      {
        if ( a1 == -1906440803 )
          return "JET_errIndexTuplesKeyTooSmall";
        if ( a1 > -1906440828 )
        {
          if ( a1 > -1906440808 )
          {
            switch ( a1 )
            {
              case -1906440807:
                return "JET_errIndexTuplesTextBinaryColumnsOnly";
              case -1906440806:
                return "JET_errIndexTuplesVarSegMacNotAllowed";
              case -1906440805:
                return "JET_errIndexTuplesInvalidLimits";
            }
            v1 = "JET_errIndexTuplesCannotRetrieveFromIndex";
            v2 = a1 == -1906440804;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440808:
                return "JET_errIndexTuplesNonUniqueOnly";
              case -1906440827:
                return "JET_errPrimaryIndexCorrupted";
              case -1906440826:
                return "JET_errSecondaryIndexCorrupted";
              case -1906440824:
                return "JET_errInvalidIndexId";
              case -1906440810:
                return "JET_errIndexTuplesSecondaryIndexOnly";
            }
            v1 = "JET_errIndexTuplesTooManyColumns";
            v2 = a1 == -1906440809;
          }
        }
        else
        {
          if ( a1 == -1906440828 )
            return "JET_errIndexBuildCorrupted";
          if ( a1 > -1906440836 )
          {
            switch ( a1 )
            {
              case -1906440835:
                return "JET_errIndexMustStay";
              case -1906440834:
                return "JET_errIndexInvalidDef";
              case -1906440831:
                return "JET_errInvalidCreateIndex";
              case -1906440830:
                return "JET_errTooManyOpenIndexes";
            }
            v1 = "JET_errMultiValuedIndexViolation";
            v2 = a1 == -1906440829;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440836:
                return "JET_errIndexNotFound";
              case -1906440911:
                return "JET_errClientRequestToStopJetService";
              case -1906440910:
                return "JET_errCannotAddFixedVarColumnToDerivedTable";
              case -1906440839:
                return "JET_errIndexCantBuild";
              case -1906440838:
                return "JET_errIndexHasPrimary";
            }
            v1 = "JET_errIndexDuplicate";
            v2 = a1 == -1906440837;
          }
        }
        goto LABEL_514;
      }
      switch ( a1 )
      {
        case -1906440739:
          result = "JET_errColumnLong";
          break;
        case -1906440738:
          result = "JET_errColumnNoChunk";
          break;
        case -1906440737:
          result = "JET_errColumnDoesNotFit";
          break;
        case -1906440736:
          result = "JET_errNullInvalid";
          break;
        case -1906440735:
          result = "JET_errColumnIndexed";
          break;
        case -1906440734:
          result = "JET_errColumnTooBig";
          break;
        case -1906440733:
          result = "JET_errColumnNotFound";
          break;
        case -1906440732:
          result = "JET_errColumnDuplicate";
          break;
        case -1906440731:
          result = "JET_errMultiValuedColumnMustBeTagged";
          break;
        case -1906440730:
          result = "JET_errColumnRedundant";
          break;
        case -1906440729:
          result = "JET_errInvalidColumnType";
          break;
        case -1906440726:
          result = "JET_errTaggedNotNULL";
          break;
        case -1906440725:
          result = "JET_errNoCurrentIndex";
          break;
        case -1906440724:
          result = "JET_errKeyIsMade";
          break;
        case -1906440723:
          result = "JET_errBadColumnId";
          break;
        case -1906440722:
          result = "JET_errBadItagSequence";
          break;
        case -1906440721:
          result = "JET_errColumnInRelationship";
          break;
        case -1906440719:
          result = "JET_errCannotBeTagged";
          break;
        case -1906440716:
          result = "JET_errDefaultValueTooBig";
          break;
        case -1906440715:
          result = "JET_errMultiValuedDuplicate";
          break;
        case -1906440714:
          result = "JET_errLVCorrupted";
          break;
        case -1906440712:
          result = "JET_errMultiValuedDuplicateAfterTruncation";
          break;
        default:
          return "Unknown Error";
      }
    }
    else
    {
      if ( a1 == -1906440912 )
        return "JET_errInvalidSettings";
      if ( a1 > -1906441018 )
      {
        if ( a1 > -1906440927 )
        {
          if ( a1 > -1906440918 )
          {
            switch ( a1 )
            {
              case -1906440917:
                return "JET_errFixedDDL";
              case -1906440916:
                return "JET_errFixedInheritedDDL";
              case -1906440915:
                return "JET_errCannotNestDDL";
            }
            v1 = "JET_errDDLNotInheritable";
            v2 = a1 == -1906440914;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440918:
                return "JET_errExclusiveTableLockRequired";
              case -1906440926:
                return "JET_errObjectDuplicate";
              case -1906440924:
                return "JET_errInvalidObject";
              case -1906440923:
                return "JET_errCannotDeleteTempTable";
              case -1906440922:
                return "JET_errCannotDeleteSystemTable";
            }
            v1 = "JET_errCannotDeleteTemplateTable";
            v2 = a1 == -1906440921;
          }
        }
        else
        {
          if ( a1 == -1906440927 )
            return "JET_errTooManyOpenTablesAndCleanupTimedOut";
          if ( a1 > -1906440935 )
          {
            switch ( a1 )
            {
              case -1906440933:
                return "JET_errDensityInvalid";
              case -1906440932:
                return "JET_errTableNotEmpty";
              case -1906440930:
                return "JET_errInvalidTableId";
              case -1906440929:
                return "JET_errTooManyOpenTables";
            }
            v1 = "JET_errIllegalOperation";
            v2 = a1 == -1906440928;
          }
          else
          {
            switch ( a1 )
            {
              case -1906440935:
                return "JET_errObjectNotFound";
              case -1906441016:
                return "JET_errDatabaseCorruptedNoRepair";
              case -1906441015:
                return "JET_errInvalidCreateDbVersion";
              case -1906440938:
                return "JET_errTableLocked";
              case -1906440937:
                return "JET_errTableDuplicate";
            }
            v1 = "JET_errTableInUse";
            v2 = a1 == -1906440936;
          }
        }
        goto LABEL_514;
      }
      if ( a1 == -1906441018 )
        return "JET_errDatabaseSignInUse";
      if ( a1 <= -1906441029 )
      {
        if ( a1 == -1906441029 )
          return "JET_errDatabase400Format";
        if ( a1 > -1906441035 )
        {
          switch ( a1 )
          {
            case -1906441034:
              return "JET_errDatabaseCorrupted";
            case -1906441033:
              return "JET_errDatabaseLocked";
            case -1906441032:
              return "JET_errCannotDisableVersioning";
            case -1906441031:
              return "JET_errInvalidDatabaseVersion";
          }
          v1 = "JET_errDatabase200Format";
          v2 = a1 == -1906441030;
        }
        else
        {
          switch ( a1 )
          {
            case -1906441035:
              return "JET_errDatabaseInvalidPages";
            case -1906441124:
              return "JET_errDirtyShutdown";
            case -1906441039:
              return "JET_errDatabaseDuplicate";
            case -1906441038:
              return "JET_errDatabaseInUse";
            case -1906441037:
              return "JET_errDatabaseNotFound";
          }
          v1 = "JET_errDatabaseInvalidName";
          v2 = a1 == -1906441036;
        }
        goto LABEL_514;
      }
      switch ( a1 )
      {
        case -1906441028:
          result = "JET_errDatabase500Format";
          break;
        case -1906441027:
          result = "JET_errPageSizeMismatch";
          break;
        case -1906441026:
          result = "JET_errTooManyInstances";
          break;
        case -1906441025:
          result = "JET_errDatabaseSharingViolation";
          break;
        case -1906441024:
          result = "JET_errAttachedDatabaseMismatch";
          break;
        case -1906441023:
          result = "JET_errDatabaseInvalidPath";
          break;
        case -1906441022:
          result = "JET_errDatabaseIdInUse";
          break;
        case -1906441021:
          result = "JET_errForceDetachNotAllowed";
          break;
        case -1906441020:
          result = "JET_errCatalogCorrupted";
          break;
        case -1906441019:
          result = "JET_errPartiallyAttachedDB";
          break;
        default:
          return "Unknown Error";
      }
    }
  }
  else
  {
    if ( a1 == -1906441125 )
      return "JET_errInvalidInstance";
    if ( a1 > -1906441660 )
    {
      if ( a1 > -1906441195 )
      {
        switch ( a1 )
        {
          case -1906441194:
            result = "JET_errColumnInUse";
            break;
          case -1906441193:
            result = "JET_errInvalidBufferSize";
            break;
          case -1906441192:
            result = "JET_errColumnNotUpdatable";
            break;
          case -1906441189:
            result = "JET_errIndexInUse";
            break;
          case -1906441188:
            result = "JET_errLinkNotSupported";
            break;
          case -1906441187:
            result = "JET_errNullKeyDisallowed";
            break;
          case -1906441186:
            result = "JET_errNotInTransaction";
            break;
          case -1906441181:
            result = "JET_errTooManyActiveUsers";
            break;
          case -1906441179:
            result = "JET_errInvalidCountry";
            break;
          case -1906441178:
            result = "JET_errInvalidLanguageId";
            break;
          case -1906441177:
            result = "JET_errInvalidCodePage";
            break;
          case -1906441176:
            result = "JET_errInvalidLCMapStringFlags";
            break;
          case -1906441175:
            result = "JET_errVersionStoreEntryTooBig";
            break;
          case -1906441174:
            result = "JET_errVersionStoreOutOfMemoryAndCleanupTimedOut";
            break;
          case -1906441171:
            result = "JET_errVersionStoreOutOfMemory";
            break;
          case -1906441169:
            result = "JET_errCannotIndex";
            break;
          case -1906441168:
            result = "JET_errRecordNotDeleted";
            break;
          case -1906441167:
            result = "JET_errTooManyMempoolEntries";
            break;
          case -1906441166:
            result = "JET_errOutOfObjectIDs";
            break;
          case -1906441165:
            result = "JET_errOutOfLongValueIDs";
            break;
          case -1906441164:
            result = "JET_errOutOfAutoincrementValues";
            break;
          case -1906441163:
            result = "JET_errOutOfDbtimeValues";
            break;
          case -1906441162:
            result = "JET_errOutOfSequentialIndexValues";
            break;
          case -1906441160:
            result = "JET_errRunningInOneInstanceMode";
            break;
          case -1906441159:
            result = "JET_errRunningInMultiInstanceMode";
            break;
          case -1906441158:
            result = "JET_errSystemParamsAlreadySet";
            break;
          case -1906441157:
            result = "JET_errSystemPathInUse";
            break;
          case -1906441156:
            result = "JET_errLogFilePathInUse";
            break;
          case -1906441155:
            result = "JET_errTempPathInUse";
            break;
          case -1906441154:
            result = "JET_errInstanceNameInUse";
            break;
          case -1906441150:
            result = "JET_errInstanceUnavailable";
            break;
          case -1906441149:
            result = "JET_errDatabaseUnavailable";
            break;
          case -1906441148:
            result = "JET_errInstanceUnavailableDueToFatalLogDiskFull";
            break;
          case -1906441139:
            result = "JET_errOutOfSessions";
            break;
          case -1906441138:
            result = "JET_errWriteConflict";
            break;
          case -1906441137:
            result = "JET_errTransTooDeep";
            break;
          case -1906441136:
            result = "JET_errInvalidSesid";
            break;
          case -1906441135:
            result = "JET_errWriteConflictPrimaryIndex";
            break;
          case -1906441132:
            result = "JET_errInTransaction";
            break;
          case -1906441131:
            result = "JET_errRollbackRequired";
            break;
          case -1906441130:
            result = "JET_errTransReadOnly";
            break;
          case -1906441129:
            result = "JET_errSessionWriteConflict";
            break;
          case -1906441128:
            result = "JET_errRecordTooBigForBackwardCompatibility";
            break;
          case -1906441127:
            result = "JET_errCannotMaterializeForwardOnlySort";
            break;
          case -1906441126:
            result = "JET_errSesidTableIdMismatch";
            break;
          default:
            return "Unknown Error";
        }
      }
      else
      {
        if ( a1 == -1906441195 )
          return "JET_errInvalidBookmark";
        if ( a1 <= -1906441227 )
        {
          if ( a1 == -1906441227 )
            return "JET_errOutOfCursors";
          if ( a1 > -1906441626 )
          {
            if ( a1 > -1906441238 )
            {
              switch ( a1 )
              {
                case -1906441237:
                  return "JET_errInvalidParameter";
                case -1906441232:
                  return "JET_errDatabaseFileReadOnly";
                case -1906441230:
                  return "JET_errInvalidDatabaseId";
              }
              v1 = "JET_errOutOfDatabaseSpace";
              v2 = a1 == -1906441228;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441238:
                  return "JET_errInvalidName";
                case -1906441625:
                  return "JET_errRestoreOfNonBackupDatabase";
                case -1906441624:
                  return "JET_errLogFileNotCopied";
                case -1906441340:
                  return "JET_errInvalidGrbit";
                case -1906441240:
                  return "JET_errTermInProgress";
              }
              v1 = "JET_errFeatureNotAvailable";
              v2 = a1 == -1906441239;
            }
          }
          else
          {
            if ( a1 == -1906441626 )
              return "JET_errCheckpointDepthTooDeep";
            if ( a1 > -1906441639 )
            {
              switch ( a1 )
              {
                case -1906441638:
                  return "JET_errUnicodeTranslationFail";
                case -1906441637:
                  return "JET_errUnicodeNormalizationNotSupported";
                case -1906441630:
                  return "JET_errExistingLogFileHasBadSignature";
                case -1906441629:
                  return "JET_errExistingLogFileIsNotContiguous";
              }
              v1 = "JET_errLogReadVerifyFailure";
              v2 = a1 == -1906441628;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441639:
                  return "JET_errUnicodeTranslationBufferTooSmall";
                case -1906441659:
                  return "JET_errSoftRecoveryOnSnapshot";
                case -1906441658:
                  return "JET_errCommittedLogFilesMissing";
                case -1906441657:
                  return "JET_errSectorSizeNotSupported";
                case -1906441656:
                  return "JET_errRecoveredWithoutUndoDatabasesConsistent";
              }
              v1 = "JET_errCommittedLogFileCorrupt";
              v2 = a1 == -1906441654;
            }
          }
          goto LABEL_514;
        }
        switch ( a1 )
        {
          case -1906441226:
            result = "JET_errOutOfBuffers";
            break;
          case -1906441225:
            result = "JET_errTooManyIndexes";
            break;
          case -1906441224:
            result = "JET_errTooManyKeys";
            break;
          case -1906441223:
            result = "JET_errRecordDeleted";
            break;
          case -1906441222:
            result = "JET_errReadVerifyFailure";
            break;
          case -1906441221:
            result = "JET_errPageNotInitialized";
            break;
          case -1906441220:
            result = "JET_errOutOfFileHandles";
            break;
          case -1906441218:
            result = "JET_errDiskIO";
            break;
          case -1906441217:
            result = "JET_errInvalidPath";
            break;
          case -1906441216:
            result = "JET_errInvalidSystemPath";
            break;
          case -1906441215:
            result = "JET_errInvalidLogDirectory";
            break;
          case -1906441214:
            result = "JET_errRecordTooBig";
            break;
          case -1906441213:
            result = "JET_errTooManyOpenDatabases";
            break;
          case -1906441212:
            result = "JET_errInvalidDatabase";
            break;
          case -1906441211:
            result = "JET_errNotInitialized";
            break;
          case -1906441210:
            result = "JET_errAlreadyInitialized";
            break;
          case -1906441209:
            result = "JET_errInitInProgress";
            break;
          case -1906441208:
            result = "JET_errFileAccessDenied";
            break;
          case -1906441202:
            result = "JET_errBufferTooSmall";
            break;
          case -1906441200:
            result = "JET_errTooManyColumns";
            break;
          case -1906441197:
            result = "JET_errContainerNotEmpty";
            break;
          case -1906441196:
            result = "JET_errInvalidFilename";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
    else
    {
      if ( a1 == -1906441660 )
        return "JET_errDatabasesNotFromSameSnapshot";
      if ( a1 > -1906441714 )
      {
        switch ( a1 )
        {
          case -1906441713:
            result = "JET_errRecoveredWithErrors";
            break;
          case -1906441712:
            result = "JET_errMissingLogFile";
            break;
          case -1906441711:
            result = "JET_errLogDiskFull";
            break;
          case -1906441710:
            result = "JET_errBadLogSignature";
            break;
          case -1906441709:
            result = "JET_errBadDbSignature";
            break;
          case -1906441708:
            result = "JET_errBadCheckpointSignature";
            break;
          case -1906441707:
            result = "JET_errCheckpointCorrupt";
            break;
          case -1906441706:
            result = "JET_errMissingPatchPage";
            break;
          case -1906441705:
            result = "JET_errBadPatchPage";
            break;
          case -1906441704:
            result = "JET_errRedoAbruptEnded";
            break;
          case -1906441702:
            result = "JET_errPatchFileMissing";
            break;
          case -1906441701:
            result = "JET_errDatabaseLogSetMismatch";
            break;
          case -1906441700:
            result = "JET_errDatabaseStreamingFileMismatch";
            break;
          case -1906441699:
            result = "JET_errLogFileSizeMismatch";
            break;
          case -1906441698:
            result = "JET_errCheckpointFileNotFound";
            break;
          case -1906441697:
            result = "JET_errRequiredLogFilesMissing";
            break;
          case -1906441696:
            result = "JET_errSoftRecoveryOnBackupDatabase";
            break;
          case -1906441695:
            result = "JET_errLogFileSizeMismatchDatabasesConsistent";
            break;
          case -1906441694:
            result = "JET_errLogSectorSizeMismatch";
            break;
          case -1906441693:
            result = "JET_errLogSectorSizeMismatchDatabasesConsistent";
            break;
          case -1906441692:
            result = "JET_errLogSequenceEndDatabasesConsistent";
            break;
          case -1906441691:
            result = "JET_errStreamingDataNotLogged";
            break;
          case -1906441690:
            result = "JET_errDatabaseDirtyShutdown";
            break;
          case -1906441689:
            result = "JET_errConsistentTimeMismatch";
            break;
          case -1906441688:
            result = "JET_errDatabasePatchFileMismatch";
            break;
          case -1906441687:
            result = "JET_errEndingRestoreLogTooLow";
            break;
          case -1906441686:
            result = "JET_errStartingRestoreLogTooHigh";
            break;
          case -1906441685:
            result = "JET_errGivenLogFileHasBadSignature";
            break;
          case -1906441684:
            result = "JET_errGivenLogFileIsNotContiguous";
            break;
          case -1906441683:
            result = "JET_errMissingRestoreLogFiles";
            break;
          case -1906441680:
            result = "JET_errMissingFullBackup";
            break;
          case -1906441679:
            result = "JET_errBadBackupDatabaseSize";
            break;
          case -1906441678:
            result = "JET_errDatabaseAlreadyUpgraded";
            break;
          case -1906441677:
            result = "JET_errDatabaseIncompleteUpgrade";
            break;
          case -1906441675:
            result = "JET_errMissingCurrentLogFiles";
            break;
          case -1906441674:
            result = "JET_errDbTimeTooOld";
            break;
          case -1906441673:
            result = "JET_errDbTimeTooNew";
            break;
          case -1906441671:
            result = "JET_errMissingFileToBackup";
            break;
          case -1906441670:
            result = "JET_errLogTornWriteDuringHardRestore";
            break;
          case -1906441669:
            result = "JET_errLogTornWriteDuringHardRecovery";
            break;
          case -1906441667:
            result = "JET_errLogCorruptDuringHardRestore";
            break;
          case -1906441666:
            result = "JET_errLogCorruptDuringHardRecovery";
            break;
          case -1906441665:
            result = "JET_errMustDisableLoggingForDbUpgrade";
            break;
          case -1906441663:
            result = "JET_errBadRestoreTargetInstance";
            break;
          case -1906441661:
            result = "JET_errRecoveredWithoutUndo";
            break;
          default:
            return "Unknown Error";
        }
      }
      else
      {
        if ( a1 == -1906441714 )
          return "JET_errInvalidBackup";
        if ( a1 <= -1906441894 )
        {
          if ( a1 == -1906441894 )
            return "JET_errKeyTruncated";
          if ( a1 > -1906441917 )
          {
            if ( a1 > -1906441900 )
            {
              switch ( a1 )
              {
                case -1906441899:
                  return "JET_errSPAvailExtCorrupted";
                case -1906441898:
                  return "JET_errSPAvailExtCacheOutOfMemory";
                case -1906441897:
                  return "JET_errSPOwnExtCorrupted";
              }
              v1 = "JET_errDbTimeCorrupted";
              v2 = a1 == -1906441896;
            }
            else
            {
              switch ( a1 )
              {
                case -1906441900:
                  return "JET_errSPAvailExtCacheOutOfSync";
                case -1906441916:
                  return "JET_errKeyBoundary";
                case -1906441913:
                  return "JET_errBadPageLink";
                case -1906441912:
                  return "JET_errBadBookmark";
                case -1906441906:
                  return "JET_errNTSystemCallFailed";
              }
              v1 = "JET_errBadParentPageLink";
              v2 = a1 == -1906441902;
            }
          }
          else
          {
            if ( a1 == -1906441917 )
              return "JET_errPageBoundary";
            if ( a1 > -1906442137 )
            {
              switch ( a1 )
              {
                case -1906442135:
                  return "JET_errTooManyIO";
                case -1906442134:
                  return "JET_errTaskDropped";
                case -1906442133:
                  return "JET_errInternalError";
                case -1906441985:
                  return "JET_errDatabaseBufferDependenciesCorrupted";
              }
              v1 = "JET_errPreviousVersion";
              v2 = a1 == -1906441918;
            }
            else
            {
              switch ( a1 )
              {
                case -1906442137:
                  return "JET_errOutOfThreads";
                case -2147024882:
                  return "JET_errOutOfMemory";
                case -1906442239:
                  return "JET_wrnNyi";
                case -1906442140:
                  return "JET_errRfsFailure";
                case -1906442139:
                  return "JET_errRfsNotArmed";
              }
              v1 = "JET_errFileClose";
              v2 = a1 == -1906442138;
            }
          }
          goto LABEL_514;
        }
        if ( a1 <= -1906441727 )
        {
          if ( a1 == -1906441727 )
            return "JET_errLogGenerationMismatch";
          if ( a1 > -1906441735 )
          {
            switch ( a1 )
            {
              case -1906441734:
                return "JET_errRestoreInProgress";
              case -1906441731:
                return "JET_errMissingPreviousLogFile";
              case -1906441730:
                return "JET_errLogWriteFail";
              case -1906441729:
                return "JET_errLogDisabledDueToRecoveryFailure";
            }
            v1 = "JET_errCannotLogDuringRecoveryRedo";
            v2 = a1 == -1906441728;
          }
          else
          {
            switch ( a1 )
            {
              case -1906441735:
                return "JET_errBackupInProgress";
              case -1906441832:
                return "JET_errKeyTooBig";
              case -1906441740:
                return "JET_errInvalidLoggedOperation";
              case -1906441739:
                return "JET_errLogFileCorrupt";
              case -1906441737:
                return "JET_errNoBackupDirectory";
            }
            v1 = "JET_errBackupDirectoryNotEmpty";
            v2 = a1 == -1906441736;
          }
          goto LABEL_514;
        }
        switch ( a1 )
        {
          case -1906441726:
            result = "JET_errBadLogVersion";
            break;
          case -1906441725:
            result = "JET_errInvalidLogSequence";
            break;
          case -1906441724:
            result = "JET_errLoggingDisabled";
            break;
          case -1906441723:
            result = "JET_errLogBufferTooSmall";
            break;
          case -1906441721:
            result = "JET_errLogSequenceEnd";
            break;
          case -1906441720:
            result = "JET_errNoBackup";
            break;
          case -1906441719:
            result = "JET_errInvalidBackupSequence";
            break;
          case -1906441717:
            result = "JET_errBackupNotAllowedYet";
            break;
          case -1906441716:
            result = "JET_errDeleteBackupFileFail";
            break;
          case -1906441715:
            result = "JET_errMakeBackupDirectoryFail";
            break;
          default:
            return "Unknown Error";
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018c50  mov     eax, 8E5E045Bh
0x140018c55  cmp     ecx, eax
0x140018c57  jg      loc_140019522
0x140018c5d  jz      loc_14001951A
0x140018c63  mov     eax, 8E5E0244h
0x140018c68  cmp     ecx, eax
0x140018c6a  jg      loc_140019101
0x140018c70  jz      loc_1400190F9
0x140018c76  mov     eax, 8E5E020Eh
0x140018c7b  cmp     ecx, eax
0x140018c7d  jg      loc_140018F6C
0x140018c83  jz      loc_140018F64
0x140018c89  mov     eax, 8E5E015Ah
0x140018c8e  cmp     ecx, eax
0x140018c90  jg      loc_140018E1D
0x140018c96  jz      loc_140018E15
0x140018c9c  mov     eax, 8E5E0143h
0x140018ca1  cmp     ecx, eax
0x140018ca3  jg      loc_140018D6E
0x140018ca9  jz      loc_140018D66
0x140018caf  mov     eax, 8E5E0067h
0x140018cb4  cmp     ecx, eax
0x140018cb6  jg      short loc_140018D14
0x140018cb8  jz      short loc_140018D0C
0x140018cba  cmp     ecx, 8007000Eh
0x140018cc0  jz      short loc_140018D04
0x140018cc2  cmp     ecx, 8E5E0001h
0x140018cc8  jz      short loc_140018CFC
0x140018cca  cmp     ecx, 8E5E0064h
0x140018cd0  jz      short loc_140018CF4
0x140018cd2  cmp     ecx, 8E5E0065h
0x140018cd8  jz      short loc_140018CEC
0x140018cda  lea     rdx, aJetErrfileclos; "JET_errFileClose"
0x140018ce1  cmp     ecx, 8E5E0066h
0x140018ce7  jmp     loc_140019E1B
0x140018cec  lea     rax, aJetErrrfsnotar; "JET_errRfsNotArmed"
0x140018cf3  retn
0x140018cf4  lea     rax, aJetErrrfsfailu; "JET_errRfsFailure"
0x140018cfb  retn
0x140018cfc  lea     rax, aJetWrnnyi; "JET_wrnNyi"
0x140018d03  retn
0x140018d04  lea     rax, aJetErroutofmem; "JET_errOutOfMemory"
0x140018d0b  retn
0x140018d0c  lea     rax, aJetErroutofthr; "JET_errOutOfThreads"
0x140018d13  retn
0x140018d14  cmp     ecx, 8E5E0069h
0x140018d1a  jz      short loc_140018D5E
0x140018d1c  cmp     ecx, 8E5E006Ah
0x140018d22  jz      short loc_140018D56
0x140018d24  cmp     ecx, 8E5E006Bh
0x140018d2a  jz      short loc_140018D4E
0x140018d2c  cmp     ecx, 8E5E00FFh
0x140018d32  jz      short loc_140018D46
0x140018d34  lea     rdx, aJetErrprevious; "JET_errPreviousVersion"
0x140018d3b  cmp     ecx, 8E5E0142h
0x140018d41  jmp     loc_140019E1B
0x140018d46  lea     rax, aJetErrdatabase_13; "JET_errDatabaseBufferDependenciesCorrup"...
0x140018d4d  retn
0x140018d4e  lea     rax, aJetErrinternal; "JET_errInternalError"
0x140018d55  retn
0x140018d56  lea     rax, aJetErrtaskdrop; "JET_errTaskDropped"
0x140018d5d  retn
0x140018d5e  lea     rax, aJetErrtoomanyi; "JET_errTooManyIO"
0x140018d65  retn
0x140018d66  lea     rax, aJetErrpageboun; "JET_errPageBoundary"
0x140018d6d  retn
0x140018d6e  mov     eax, 8E5E0154h
0x140018d73  cmp     ecx, eax
0x140018d75  jg      short loc_140018DD3
0x140018d77  jz      short loc_140018DCB
0x140018d79  cmp     ecx, 8E5E0144h
0x140018d7f  jz      short loc_140018DC3
0x140018d81  cmp     ecx, 8E5E0147h
0x140018d87  jz      short loc_140018DBB
0x140018d89  cmp     ecx, 8E5E0148h
0x140018d8f  jz      short loc_140018DB3
0x140018d91  cmp     ecx, 8E5E014Eh
0x140018d97  jz      short loc_140018DAB
0x140018d99  lea     rdx, aJetErrbadparen; "JET_errBadParentPageLink"
0x140018da0  cmp     ecx, 8E5E0152h
0x140018da6  jmp     loc_140019E1B
0x140018dab  lea     rax, aJetErrntsystem; "JET_errNTSystemCallFailed"
0x140018db2  retn
0x140018db3  lea     rax, aJetErrbadbookm; "JET_errBadBookmark"
0x140018dba  retn
0x140018dbb  lea     rax, aJetErrbadpagel; "JET_errBadPageLink"
0x140018dc2  retn
0x140018dc3  lea     rax, aJetErrkeybound; "JET_errKeyBoundary"
0x140018dca  retn
0x140018dcb  lea     rax, aJetErrspavaile_1; "JET_errSPAvailExtCacheOutOfSync"
0x140018dd2  retn
0x140018dd3  cmp     ecx, 8E5E0155h
0x140018dd9  jz      short loc_140018E0D
0x140018ddb  cmp     ecx, 8E5E0156h
0x140018de1  jz      short loc_140018E05
0x140018de3  cmp     ecx, 8E5E0157h
0x140018de9  jz      short loc_140018DFD
0x140018deb  lea     rdx, aJetErrdbtimeco; "JET_errDbTimeCorrupted"
0x140018df2  cmp     ecx, 8E5E0158h
0x140018df8  jmp     loc_140019E1B
0x140018dfd  lea     rax, aJetErrspownext; "JET_errSPOwnExtCorrupted"
0x140018e04  retn
0x140018e05  lea     rax, aJetErrspavaile_0; "JET_errSPAvailExtCacheOutOfMemory"
0x140018e0c  retn
0x140018e0d  lea     rax, aJetErrspavaile; "JET_errSPAvailExtCorrupted"
0x140018e14  retn
0x140018e15  lea     rax, aJetErrkeytrunc; "JET_errKeyTruncated"
0x140018e1c  retn
0x140018e1d  mov     eax, 8E5E0201h
0x140018e22  cmp     ecx, eax
0x140018e24  jg      loc_140018EEF
0x140018e2a  jz      loc_140018EE7
0x140018e30  mov     eax, 8E5E01F9h
0x140018e35  cmp     ecx, eax
0x140018e37  jg      short loc_140018E95
0x140018e39  jz      short loc_140018E8D
0x140018e3b  cmp     ecx, 8E5E0198h
0x140018e41  jz      short loc_140018E85
0x140018e43  cmp     ecx, 8E5E01F4h
0x140018e49  jz      short loc_140018E7D
0x140018e4b  cmp     ecx, 8E5E01F5h
0x140018e51  jz      short loc_140018E75
0x140018e53  cmp     ecx, 8E5E01F7h
0x140018e59  jz      short loc_140018E6D
0x140018e5b  lea     rdx, aJetErrbackupdi; "JET_errBackupDirectoryNotEmpty"
0x140018e62  cmp     ecx, 8E5E01F8h
0x140018e68  jmp     loc_140019E1B
0x140018e6d  lea     rax, aJetErrnobackup_0; "JET_errNoBackupDirectory"
0x140018e74  retn
0x140018e75  lea     rax, aJetErrlogfilec; "JET_errLogFileCorrupt"
0x140018e7c  retn
0x140018e7d  lea     rax, aJetErrinvalidl_0; "JET_errInvalidLoggedOperation"
0x140018e84  retn
0x140018e85  lea     rax, aJetErrkeytoobi; "JET_errKeyTooBig"
0x140018e8c  retn
0x140018e8d  lea     rax, aJetErrbackupin; "JET_errBackupInProgress"
0x140018e94  retn
0x140018e95  cmp     ecx, 8E5E01FAh
0x140018e9b  jz      short loc_140018EDF
0x140018e9d  cmp     ecx, 8E5E01FDh
0x140018ea3  jz      short loc_140018ED7
0x140018ea5  cmp     ecx, 8E5E01FEh
0x140018eab  jz      short loc_140018ECF
0x140018ead  cmp     ecx, 8E5E01FFh
0x140018eb3  jz      short loc_140018EC7
0x140018eb5  lea     rdx, aJetErrcannotlo; "JET_errCannotLogDuringRecoveryRedo"
0x140018ebc  cmp     ecx, 8E5E0200h
0x140018ec2  jmp     loc_140019E1B
0x140018ec7  lea     rax, aJetErrlogdisab; "JET_errLogDisabledDueToRecoveryFailure"
0x140018ece  retn
0x140018ecf  lea     rax, aJetErrlogwrite; "JET_errLogWriteFail"
0x140018ed6  retn
0x140018ed7  lea     rax, aJetErrmissingp; "JET_errMissingPreviousLogFile"
0x140018ede  retn
0x140018edf  lea     rax, aJetErrrestorei; "JET_errRestoreInProgress"
0x140018ee6  retn
0x140018ee7  lea     rax, aJetErrloggener; "JET_errLogGenerationMismatch"
0x140018eee  retn
0x140018eef  add     ecx, 71A1FDFEh; switch 12 cases
0x140018ef5  cmp     ecx, 0Bh
0x140018ef8  ja      def_140018F12; jumptable 0000000140018F12 default case, cases -1906441722,-1906441718
0x140018efe  lea     rdx, cs:140000000h
0x140018f05  movsxd  rax, ecx
0x140018f08  mov     eax, ds:(jpt_140018F12 - 140000000h)[rdx+rax*4]
0x140018f0f  add     rax, rdx
0x140018f12  jmp     rax; switch jump
0x140018f14  lea     rax, aJetErrbadlogve; jumptable 0000000140018F12 case -1906441726
0x140018f1b  retn
0x140018f1c  lea     rax, aJetErrinvalidl; jumptable 0000000140018F12 case -1906441725
0x140018f23  retn
0x140018f24  lea     rax, aJetErrloggingd; jumptable 0000000140018F12 case -1906441724
0x140018f2b  retn
0x140018f2c  lea     rax, aJetErrlogbuffe; jumptable 0000000140018F12 case -1906441723
0x140018f33  retn
0x140018f34  lea     rax, aJetErrlogseque; jumptable 0000000140018F12 case -1906441721
0x140018f3b  retn
0x140018f3c  lea     rax, aJetErrnobackup; jumptable 0000000140018F12 case -1906441720
0x140018f43  retn
0x140018f44  lea     rax, aJetErrinvalidb_1; jumptable 0000000140018F12 case -1906441719
0x140018f4b  retn
0x140018f4c  lea     rax, aJetErrbackupno; jumptable 0000000140018F12 case -1906441717
0x140018f53  retn
0x140018f54  lea     rax, aJetErrdeleteba; jumptable 0000000140018F12 case -1906441716
0x140018f5b  retn
0x140018f5c  lea     rax, aJetErrmakeback; jumptable 0000000140018F12 case -1906441715
0x140018f63  retn
0x140018f64  lea     rax, aJetErrinvalidb_0; "JET_errInvalidBackup"
0x140018f6b  retn
0x140018f6c  add     ecx, 71A1FDF1h; switch 53 cases
0x140018f72  cmp     ecx, 34h
0x140018f75  ja      def_140018F12; jumptable 0000000140018F12 default case, cases -1906441722,-1906441718
0x140018f7b  lea     rdx, cs:140000000h
0x140018f82  movsxd  rax, ecx
0x140018f85  mov     eax, ds:(jpt_140018F8F - 140000000h)[rdx+rax*4]
0x140018f8c  add     rax, rdx
0x140018f8f  jmp     rax; switch jump
0x140018f91  lea     rax, aJetErrrecovere; jumptable 0000000140018F8F case -1906441713
0x140018f98  retn
0x140018f99  lea     rax, aJetErrmissingl; jumptable 0000000140018F8F case -1906441712
0x140018fa0  retn
0x140018fa1  lea     rax, aJetErrlogdiskf; jumptable 0000000140018F8F case -1906441711
0x140018fa8  retn
0x140018fa9  lea     rax, aJetErrbadlogsi; jumptable 0000000140018F8F case -1906441710
0x140018fb0  retn
0x140018fb1  lea     rax, aJetErrbaddbsig; jumptable 0000000140018F8F case -1906441709
0x140018fb8  retn
0x140018fb9  lea     rax, aJetErrbadcheck; jumptable 0000000140018F8F case -1906441708
0x140018fc0  retn
0x140018fc1  lea     rax, aJetErrcheckpoi; jumptable 0000000140018F8F case -1906441707
0x140018fc8  retn
0x140018fc9  lea     rax, aJetErrmissingp_0; jumptable 0000000140018F8F case -1906441706
0x140018fd0  retn
0x140018fd1  lea     rax, aJetErrbadpatch; jumptable 0000000140018F8F case -1906441705
0x140018fd8  retn
0x140018fd9  lea     rax, aJetErrredoabru; jumptable 0000000140018F8F case -1906441704
0x140018fe0  retn
0x140018fe1  lea     rax, aJetErrpatchfil; jumptable 0000000140018F8F case -1906441702
0x140018fe8  retn
0x140018fe9  lea     rax, aJetErrdatabase_12; jumptable 0000000140018F8F case -1906441701
0x140018ff0  retn
0x140018ff1  lea     rax, aJetErrdatabase_9; jumptable 0000000140018F8F case -1906441700
0x140018ff8  retn
0x140018ff9  lea     rax, aJetErrlogfiles; jumptable 0000000140018F8F case -1906441699
0x140019000  retn
0x140019001  lea     rax, aJetErrcheckpoi_0; jumptable 0000000140018F8F case -1906441698
0x140019008  retn
0x140019009  lea     rax, aJetErrrequired; jumptable 0000000140018F8F case -1906441697
0x140019010  retn
0x140019011  lea     rax, aJetErrsoftreco_0; jumptable 0000000140018F8F case -1906441696
0x140019018  retn
0x140019019  lea     rax, aJetErrlogfiles_0; jumptable 0000000140018F8F case -1906441695
0x140019020  retn
0x140019021  lea     rax, aJetErrlogsecto_0; jumptable 0000000140018F8F case -1906441694
0x140019028  retn
0x140019029  lea     rax, aJetErrlogsecto; jumptable 0000000140018F8F case -1906441693
0x140019030  retn
0x140019031  lea     rax, aJetErrlogseque_0; jumptable 0000000140018F8F case -1906441692
0x140019038  retn
0x140019039  lea     rax, aJetErrstreamin; jumptable 0000000140018F8F case -1906441691
0x140019040  retn
0x140019041  lea     rax, aJetErrdatabase_0; jumptable 0000000140018F8F case -1906441690
0x140019048  retn
0x140019049  lea     rax, aJetErrconsiste; jumptable 0000000140018F8F case -1906441689
0x140019050  retn
0x140019051  lea     rax, aJetErrdatabase_6; jumptable 0000000140018F8F case -1906441688
0x140019058  retn
0x140019059  lea     rax, aJetErrendingre; jumptable 0000000140018F8F case -1906441687
0x140019060  retn
0x140019061  lea     rax, aJetErrstarting; jumptable 0000000140018F8F case -1906441686
0x140019068  retn
0x140019069  lea     rax, aJetErrgivenlog; jumptable 0000000140018F8F case -1906441685
0x140019070  retn
0x140019071  lea     rax, aJetErrgivenlog_0; jumptable 0000000140018F8F case -1906441684
0x140019078  retn
0x140019079  lea     rax, aJetErrmissingr; jumptable 0000000140018F8F case -1906441683
0x140019080  retn
0x140019081  lea     rax, aJetErrmissingf; jumptable 0000000140018F8F case -1906441680
0x140019088  retn
0x140019089  lea     rax, aJetErrbadbacku; jumptable 0000000140018F8F case -1906441679
0x140019090  retn
0x140019091  lea     rax, aJetErrdatabase_24; jumptable 0000000140018F8F case -1906441678
0x140019098  retn
0x140019099  lea     rax, aJetErrdatabase_4; jumptable 0000000140018F8F case -1906441677
0x1400190a0  retn
0x1400190a1  lea     rax, aJetErrmissingc; jumptable 0000000140018F8F case -1906441675
0x1400190a8  retn
0x1400190a9  lea     rax, aJetErrdbtimeto; jumptable 0000000140018F8F case -1906441674
0x1400190b0  retn
0x1400190b1  lea     rax, aJetErrdbtimeto_0; jumptable 0000000140018F8F case -1906441673
0x1400190b8  retn
0x1400190b9  lea     rax, aJetErrmissingf_0; jumptable 0000000140018F8F case -1906441671
0x1400190c0  retn
0x1400190c1  lea     rax, aJetErrlogtornw_0; jumptable 0000000140018F8F case -1906441670
0x1400190c8  retn
0x1400190c9  lea     rax, aJetErrlogtornw; jumptable 0000000140018F8F case -1906441669
0x1400190d0  retn
0x1400190d1  lea     rax, aJetErrlogcorru_1; jumptable 0000000140018F8F case -1906441667
0x1400190d8  retn
0x1400190d9  lea     rax, aJetErrlogcorru; jumptable 0000000140018F8F case -1906441666
0x1400190e0  retn
0x1400190e1  lea     rax, aJetErrmustdisa; jumptable 0000000140018F8F case -1906441665
0x1400190e8  retn
0x1400190e9  lea     rax, aJetErrbadresto; jumptable 0000000140018F8F case -1906441663
0x1400190f0  retn
0x1400190f1  lea     rax, aJetErrrecovere_0; jumptable 0000000140018F8F case -1906441661
0x1400190f8  retn
0x1400190f9  lea     rax, aJetErrdatabase_19; "JET_errDatabasesNotFromSameSnapshot"
0x140019100  retn
0x140019101  mov     eax, 8E5E0415h
0x140019106  cmp     ecx, eax
0x140019108  jg      loc_140019385
0x14001910e  jz      loc_14001937D
0x140019114  mov     eax, 8E5E03F5h
0x140019119  cmp     ecx, eax
0x14001911b  jg      loc_1400192A8
0x140019121  jz      loc_1400192A0
0x140019127  mov     eax, 8E5E0266h
0x14001912c  cmp     ecx, eax
0x14001912e  jg      loc_1400191F9
0x140019134  jz      loc_1400191F1
  ... truncated ...
```
